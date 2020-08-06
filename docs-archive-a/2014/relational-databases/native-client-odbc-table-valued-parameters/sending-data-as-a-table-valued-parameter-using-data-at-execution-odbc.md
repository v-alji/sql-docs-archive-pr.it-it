---
title: Invio di dati come parametro con valori di tabella utilizzando data-at-execution (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), sending data to a stored procedure one row at a time
ms.assetid: 361e6442-34de-4cac-bdbd-e05f04a21ce4
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f3951ef93539e003b62397f370490c89c953a01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724580"
---
# <a name="sending-data-as-a-table-valued-parameter-using-data-at-execution-odbc"></a><span data-ttu-id="272be-102">Invio di dati come parametro con valori di tabella utilizzando data-at-execution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="272be-102">Sending Data as a Table-Valued Parameter Using Data-At-Execution (ODBC)</span></span>
  <span data-ttu-id="272be-103">Questa procedura è simile alla procedura [All in Memory](sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc.md) , ma utilizza data-at-execution per il parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="272be-103">This is similar to the [All in Memory](sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc.md) procedure, but uses data-at-execution for the table-valued parameter.</span></span>  
  
 <span data-ttu-id="272be-104">Per un altro esempio che illustra i parametri con valori di tabella, vedere [usare parametri con valori di tabella &#40;&#41;ODBC ](table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="272be-104">For another sample demonstrating table-valued parameters, see [Use Table-Valued Parameters &#40;ODBC&#41;](table-valued-parameters-odbc.md).</span></span>  
  
 <span data-ttu-id="272be-105">In questo esempio, quando viene chiamato SQLExecute o SQLExecDirect, il driver restituisce SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="272be-105">In this example, when SQLExecute or SQLExecDirect is called, the driver returns SQL_NEED_DATA.</span></span> <span data-ttu-id="272be-106">L'applicazione chiama quindi SQLParamData ripetutamente fino a quando il driver non restituisce un valore diverso da SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="272be-106">The application then calls SQLParamData repeatedly until the driver returns a value other than SQL_NEED_DATA.</span></span> <span data-ttu-id="272be-107">Il driver restituisce *ParameterValuePtr* per informare l'applicazione di quale parametro richiede i dati.</span><span class="sxs-lookup"><span data-stu-id="272be-107">The driver returns *ParameterValuePtr* to inform the application which parameter it is requesting data for.</span></span> <span data-ttu-id="272be-108">L'applicazione chiama SQLPutData per fornire i dati dei parametri prima della chiamata successiva a SQLParamData.</span><span class="sxs-lookup"><span data-stu-id="272be-108">The application calls SQLPutData to supply parameter data before the next call to SQLParamData.</span></span> <span data-ttu-id="272be-109">Per un parametro con valori di tabella, la chiamata a SQLPutData indica il numero di righe preparate per il driver (in questo esempio, sempre 1).</span><span class="sxs-lookup"><span data-stu-id="272be-109">For a table-valued parameter, the call to SQLPutData indicates how many rows it has prepared for the driver (in this example, always 1).</span></span> <span data-ttu-id="272be-110">Quando tutte le righe del valore di tabella sono state passate al driver, viene chiamato SQLPutData per indicare che sono disponibili 0 righe.</span><span class="sxs-lookup"><span data-stu-id="272be-110">When all rows of the table-value have been passed to the driver, SQLPutData is called to indicate that 0 rows are available.</span></span>  
  
 <span data-ttu-id="272be-111">È possibile utilizzare i valori data-at-execution nelle righe di un valore di tabella.</span><span class="sxs-lookup"><span data-stu-id="272be-111">It is possible to use data-at-execution values within rows of a table-value.</span></span> <span data-ttu-id="272be-112">Il valore restituito da SQLParamData informa l'applicazione del valore richiesto dal driver.</span><span class="sxs-lookup"><span data-stu-id="272be-112">The value returned by SQLParamData informs the application which value the driver requires.</span></span> <span data-ttu-id="272be-113">Come per i valori dei parametri normali, è possibile chiamare SQLPutData una o più volte per un valore di colonna con valori di tabella di tipo carattere o binario.</span><span class="sxs-lookup"><span data-stu-id="272be-113">As with regular parameter values, SQLPutData can be called one or more times for a character or binary table-value column value.</span></span> <span data-ttu-id="272be-114">Ciò consente a un'applicazione di passare valori di grandi dimensioni in parti.</span><span class="sxs-lookup"><span data-stu-id="272be-114">This allows an application to pass large values in pieces.</span></span>  
  
 <span data-ttu-id="272be-115">Quando SQLPutData viene chiamato per un valore di tabella, viene usato *DataPtr* per il numero di righe disponibili (in questo esempio, sempre 1).</span><span class="sxs-lookup"><span data-stu-id="272be-115">When SQLPutData is called for a table-value, *DataPtr* is used for the number of rows available (in this example, always 1).</span></span> <span data-ttu-id="272be-116">*StrLen_or_IndPtr* deve essere sempre 0.</span><span class="sxs-lookup"><span data-stu-id="272be-116">*StrLen_or_IndPtr* must always be 0.</span></span> <span data-ttu-id="272be-117">Quando tutte le righe del valore di tabella sono state passate, viene chiamato SQLPutData con un valore *DataPtr* pari a 0.</span><span class="sxs-lookup"><span data-stu-id="272be-117">When all rows of the table-value have been passed, SQLPutData is called with a *DataPtr* value of 0.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="272be-118">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="272be-118">Prerequisite</span></span>  
 <span data-ttu-id="272be-119">Questa procedura presuppone che sia stata eseguita l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente nel server:</span><span class="sxs-lookup"><span data-stu-id="272be-119">This procedure assumes that the following [!INCLUDE[tsql](../../includes/tsql-md.md)] has been executed on the server:</span></span>  
  
```  
create type TVParam as table(ProdCode integer, Qty integer)  
create procedure TVPOrderEntry(@CustCode varchar(5), @Items TVPParam,   
            @OrdNo integer output, @OrdDate datetime output)  
         as   
         set @OrdDate = GETDATE();  
         insert into TVPOrd (OrdDate, CustCode) values (@OrdDate, @CustCode) output OrdNo);   
         select @OrdNo = SCOPE_IDENTITY();   
         insert into TVPItem (OrdNo, ProdCode, Qty)  
select @OrdNo, @Items.ProdCode, @Items.Qty   
from @Items  
```  
  
## <a name="to-send-the-data"></a><span data-ttu-id="272be-120">Per inviare i dati</span><span class="sxs-lookup"><span data-stu-id="272be-120">To Send the Data</span></span>  
  
1.  <span data-ttu-id="272be-121">Dichiarare le variabili per i parametri SQL.</span><span class="sxs-lookup"><span data-stu-id="272be-121">Declare the variables for the SQL parameters.</span></span> <span data-ttu-id="272be-122">I buffer dei parametri con valori di tabella non devono essere matrici in questo esempio. Nell'esempio viene passata una sola riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="272be-122">The buffers for table-valued parameters do not have to be arrays in this example; the example passes one row at a time.</span></span>  
  
    ```  
    SQLRETURN r;  
  
    // Variables for SQL parameters:  
    SQLCHAR CustCode[6];  
    SQLCHAR *TVP = (SQLCHAR *) "TVPInParam";  
    SQLINTEGER ProdCode, Qty;  
    SQLINTEGER OrdNo;  
    char *OrdDate[23];  
    SQLCHAR *TVP = (SQLCHAR *) "TVParam";  
    SQLINTEGER ItemNo;  
    // Variables for indicator/length variables associated with parameters:  
    SQLLEN cbCustCode, cbTVP, cbProdCode, cbQty, cbOrdNo, cbOrdDate, cbItemNo;  
    // Token returned by SQLParamData to indicate which param data is needed for:  
    SQLPOINTER ParamId;  
    ```  
  
2.  <span data-ttu-id="272be-123">Associare i parametri.</span><span class="sxs-lookup"><span data-stu-id="272be-123">Bind the parameters.</span></span> <span data-ttu-id="272be-124">*ColumnSize* è 1, ovvero viene passato al massimo una riga alla volta.</span><span class="sxs-lookup"><span data-stu-id="272be-124">*ColumnSize* is 1, meaning that at most one row is passed at a time.</span></span>  
  
    ```  
    // Bind parameters for call to TVPOrderEntryByRow.  
    r = SQLBindParameter(hstmt, 1, SQL_C_CHAR, SQL_PARAM_INPUT,SQL_VARCHAR, 5, 0, CustCode, sizeof(CustCode), &cbCustCode);  
  
    // 2 - Items TVP  
    r = SQLBindParameter(hstmt,   
        2,         // ParameterNumber  
        SQL_C_DEFAULT,   // InputOutputType  
        SQL_PARAM_INPUT,   // ValueType   
        SQL_SS_TABLE,   // Parametertype  
        1,         // ColumnSize: For a table-valued parameter this the row array size.  
        0,         // DecimalDigits: For a table-valued parameter this is always 0.   
        TVP,      // ParameterValuePtr: For a table-valued parameter this is the type name of the TVP,  
             //      and also a token returned by SQLParamData.  
        SQL_NTS,      // BufferLength: For a table-valued parameter this is the length of the type name or SQL_NTS.  
        &cbTVP);      // StrLen_or_IndPtr: For a table-valued parameter this is the number of rows input and output.  
  
    // 3 - OrdNo output  
    r = SQLBindParameter(hstmt, 3, SQL_PARAM_OUTPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &OrdNo,  
        sizeof(SQLINTEGER), &cbOrdNo);  
    // 4- OrdDate output  
    r = SQLBindParameter(hstmt, 4, SQL_PARAM_OUTPUT, SQL_C_CHAR, SQL_TYPE_TIMESTAMP, 23, 3, &OrdDate,  
        sizeof(OrdDate), &cbOrdDate);  
    ```  
  
3.  <span data-ttu-id="272be-125">Associare le colonne per il parametro con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="272be-125">Bind the columns for the table-valued parameter.</span></span>  
  
    ```  
    // Bind the table-valued parameter columns.  
    // First set focus on param 2  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 2, SQL_IS_INTEGER);  
  
    // ProdCode  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &ProdCode,  
        sizeof(SQLINTEGER), &cbProdCode);  
    // Qty  
    r = SQLBindParameter(hstmt, 2, SQL_PARAM_INPUT, SQL_C_LONG, SQL_INTEGER, 0, 0, &Qty,   
       sizeof(SQLINTEGER), &cbQty);  
  
    // Reset param focus  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 0, SQL_IS_INTEGER);  
    ```  
  
4.  <span data-ttu-id="272be-126">Inizializzare i parametri.</span><span class="sxs-lookup"><span data-stu-id="272be-126">Initialize the parameters.</span></span> <span data-ttu-id="272be-127">In questo esempio vengono impostate le dimensioni del parametro con valori di tabella su SQL_DATA_AT_EXEC, anziché su un conteggio delle righe.</span><span class="sxs-lookup"><span data-stu-id="272be-127">This example sets the size of the table-valued parameter to SQL_DATA_AT_EXEC, rather than to a row count.</span></span>  
  
    ```  
    // Initialze the TVP for row streaming.  
    cbTVP = SQL_DATA_AT_EXEC;  
  
    // Populate non-data-at-exec parameters.  
    strcpy_s((char *) CustCode ,sizeof(CustCode), "CUST1"); cbCustCode = SQL_NTS;  
    ```  
  
5.  <span data-ttu-id="272be-128">Chiamare la routine.</span><span class="sxs-lookup"><span data-stu-id="272be-128">Call the procedure.</span></span> <span data-ttu-id="272be-129">SQLExecDirect restituirà SQL_NEED_DATA perché il parametro con valori di tabella è un parametro data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="272be-129">SQLExecDirect will return SQL_NEED_DATA because the table-valued parameter is a data-at-execution parameter.</span></span>  
  
    ```  
    // Call the procedure  
    r = SQLExecDirect(hstmt, (SQLCHAR *) "{call TVPOrderEntry(?, ?, ?, ?)}",SQL_NTS);  
    ```  
  
6.  <span data-ttu-id="272be-130">Fornire i dati dei parametri data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="272be-130">Supply data-at-execution parameter data.</span></span> <span data-ttu-id="272be-131">Quando SQLParamData restituisce *ParameterValuePtr* per un parametro con valori di tabella, l'applicazione deve preparare le colonne per la riga o le righe successive del valore di tabella.</span><span class="sxs-lookup"><span data-stu-id="272be-131">When SQLParamData returns the *ParameterValuePtr* for a table-valued parameter, the application must prepare the columns for the next row or rows of the table-value.</span></span> <span data-ttu-id="272be-132">Quindi, l'applicazione chiama SQLPutData con *DataPtr* impostato sul numero di righe disponibili (in questo esempio, 1) e *StrLen_or_IndPtr* impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="272be-132">Then the application calls SQLPutData with *DataPtr* set to the number of rows available (in this example, 1) and *StrLen_or_IndPtr* set to 0.</span></span>  
  
    ```  
    // Check if parameter data is required, and get the first parameter ID token  
    if (r == SQL_NEED_DATA) {  
        r = SQLParamData(hstmt, &ParamId);  
    }  
  
    // Supply parameter row data.  
    int rowNum = 0;  
    while (r == SQL_NEED_DATA) {  
        if (ParamId == TVP) {  
       switch (rowNum) {  
           case 0: // Supply data for 1st row  
          // Populate input table-valued parameter row constituent columns.  
          ProdCode = 1215;   cbProdCode = sizeof(SQLINTEGER);   
          Qty = 5;      cbQty = sizeof(SQLINTEGER);  
          // Returning 1 for StrLenOrIndPtr indicates that a row is available.  
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 1);  
          rowNum++;  
          break;  
  
           case 1: // Supply data for the second row.  
          // Populate another table-valued parameter row as above.  
          ProdCode = 1017;   cbProdCode = sizeof(SQLINTEGER);   
          // This time supply Qty through SQLPutData.  
          Qty = 0;      cbQty = SQL_DATA_AT_EXEC;   
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 1);  
          rowNum++;  
          break;  
  
        default:  
          // Passing 0 in StrLenOrIndPtr indicates that no more table-valued parameter rows are available.  
          r = SQLPutData(hstmt, (SQLPOINTER) 1, 0);  
          break;  
           }  
        }  
        else {  
           if (ParamId == &Qty) {  
          Qty = 2;  
          // For a character or binary parameter, SQLPutData could be called  
          // multiple times to pass the value in pieces.  
          SQLPutData(hstmt, &Qty, sizeof(SQLINTEGER));  
           }  
       }  
       // Signal that parameter data is available, and get the token for   
       // the next parameter.  
       r = SQLParamData(hstmt, &ParamId);  
        }  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="272be-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="272be-133">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="272be-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="272be-134">Description</span></span>  
 <span data-ttu-id="272be-135">In questo esempio viene illustrato come utilizzare il flusso di righe, una riga per ogni chiamata a SQLPutData, con ODBC TVP, in modo analogo a come utilizzare BCP.exe per caricare i dati in un database.</span><span class="sxs-lookup"><span data-stu-id="272be-135">This sample shows that you can use row streaming, one row per call to SQLPutData, with ODBC TVP, similar to how you might use BCP.exe to load data into a database.</span></span>  
  
 <span data-ttu-id="272be-136">Prima di compilare l'esempio, modificare il nome del server nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="272be-136">Before building the sample, change the server name in the connection string.</span></span>  
  
 <span data-ttu-id="272be-137">In questo esempio viene utilizzato il database predefinito.</span><span class="sxs-lookup"><span data-stu-id="272be-137">This sample uses the default database.</span></span> <span data-ttu-id="272be-138">Prima di eseguire questo esempio, eseguire i comandi seguenti nel database che verrà utilizzato:</span><span class="sxs-lookup"><span data-stu-id="272be-138">Before running this sample, run the following commands in the database you will use:</span></span>  
  
```  
create table MCLOG (  
   biSeqNo bigint,   
   iSeries int,   
   bmRestData varbinary(max)  
)  
go  
  
-- Table type definition  
create type MCLOGType   
   as table(biSeqNo bigint, iSeries int, bmRestData varbinary(max) )  
go  
  
-- Insert procedure  
create procedure MCLOGInsert (@TableVariable MCLOGType READONLY)  
   as  
   insert into MCLog(biSeqNo,  iSeries, bmRestData)   
   select biSeqNo, iSeries, bmRestData from @TableVariable    
go  
```  
  
### <a name="code"></a><span data-ttu-id="272be-139">Codice</span><span class="sxs-lookup"><span data-stu-id="272be-139">Code</span></span>  
  
```  
#define UNICODE  
#define _UNICODE  
#define _SQLNCLI_ODBC_  
  
#include <windows.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// link to sqlncli11.lib  
  
#define SUCCESS(x) ( \  
   !((x) & 0xFFFE) \  
   )  
  
#define CHKRC(stmt) { \  
   rc = (stmt); \  
   if (!SUCCESS(rc)) { \  
      _tprintf(_T(#stmt) _T(" failed with rc = %ld\r\n"), rc); \  
      goto EXIT; \  
   } \  
};  
  
void PrintError(SQLSMALLINT HandleType, SQLHANDLE Handle) {  
   RETCODE rc = SQL_SUCCESS;  
   SQLTCHAR szSqlState[6];  
   SQLTCHAR szMessage[1024];  
   SQLSMALLINT i = 1;  
   SQLSMALLINT msgLen = 0;  
   SQLINTEGER NativeError;  
  
   i = 1;  
   while ( (rc = SQLGetDiagRec(HandleType, Handle, i, szSqlState, &NativeError, szMessage, sizeof(szMessage)/sizeof(SQLTCHAR), &msgLen)) != SQL_NO_DATA) {  
      if (!SUCCESS(rc))  
         break;  
      szMessage[msgLen] = 0;  
      szSqlState[5] = 0;  
      _tprintf(_T("SQLState=%s, NativeError=%ld, Message=%s\r\n"), szSqlState, NativeError, szMessage);  
      i++;  
   }  
}  
  
int main() {  
   RETCODE rc = SQL_SUCCESS;  
   HENV henv = SQL_NULL_HENV;  
   HDBC hdbc = SQL_NULL_HDBC;  
   SQLHSTMT hstmt = SQL_NULL_HSTMT;  
   SQLTCHAR * pszConnection = _T("DRIVER={SQL Server Native Client 10.0};Server=your_servername;Trusted_Connection=Yes;");  
  
   // insert one TVP parameter  
   SQLTCHAR * pszInsertStmt = _T("{call MCLOGInsert(?)}");  
   SQLLEN cbParamLength;  
   SQLULEN cMaxRows = 3;  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HENV, &henv));  
   CHKRC(SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0));  
   CHKRC(SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc));  
   CHKRC(SQLSetConnectAttr(hdbc, SQL_ATTR_LOGIN_TIMEOUT,reinterpret_cast<SQLPOINTER>(60),SQL_IS_UINTEGER));  
   CHKRC(SQLDriverConnect(hdbc, NULL, pszConnection, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT));  
   CHKRC(SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt));  
   CHKRC(SQLPrepare(hstmt, pszInsertStmt, SQL_NTS));  
  
   // Bind the first parameter  
   CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)1, 0, &cbParamLength));  
   // If the stored procedure is executed as T-SQL ("exec sp_insert ?, ?"), you will supply the type name.  
   // CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)lpszTVPParamType, SQL_NTS, &cbParamLengths));  
  
   // bind TVP columns  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)1, SQL_IS_INTEGER));  
  
   // for each TVP column, you can define an array to send more than one row for each SQLPutData call.  
   LONGLONG llSeqNo;  
   SQLLEN cbSeqNo = sizeof(LONGLONG);  
   LONG lSeries;  
   SQLLEN cbSeries = sizeof(LONG);  
   BYTE rgbRestData[2048];  
   SQLLEN cbRestData = SQL_DATA_AT_EXEC;  
   SQLUSMALLINT iColumn = 1;  
  
   // Bind biSeqNo   
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SBIGINT, SQL_BIGINT, sizeof(LONGLONG), 0, (SQLPOINTER)&llSeqNo, sizeof(llSeqNo), &cbSeqNo));  
  
   // Bind iSeries   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SLONG, SQL_INTEGER, sizeof(LONG), 0, (SQLPOINTER)&lSeries, sizeof(lSeries), &cbSeries));  
  
   // Bind bmRestData   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_BINARY, SQL_VARBINARY, 0, 0, (SQLPOINTER)rgbRestData, 0, &cbRestData));  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)0, SQL_IS_INTEGER));  
  
   // Set cbParamLength to SQL_DATA_AT_EXEC to indicate the TVP parameter is bound as DAE.  
   cbParamLength = SQL_DATA_AT_EXEC;  
   rc = SQLExecute(hstmt);  
  
   if (rc == SQL_NEED_DATA) {  
      SQLPOINTER ptr = NULL;  
      SQLULEN cRows = 0;  
  
      rc = ::SQLParamData(hstmt, &ptr);  
  
      while (rc == SQL_NEED_DATA) {  
         if (ptr == (SQLPOINTER)1) {  
            // it is the TVP parameter  
            if (cRows == cMaxRows) {  
               // We finish sending the last row already.  
               CHKRC(::SQLPutData(hstmt, NULL, 0));  
            }  
            else {  
               // StrLen_or_IndPtr can be changed to SQL_DATA_AT_EXEC or to a byte length before sending  
               // the actual TVP rows. SQL_DATA_AT_EXEC means send DAE data.  
               llSeqNo = cRows;  
               cbSeqNo = sizeof(LONGLONG);   // send as bound TVP column  
               lSeries = cRows + 100;  
               cbSeries = sizeof(LONG);   // send as bound TVP column  
               cbRestData = SQL_DATA_AT_EXEC;   // send as DAE TVP column  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)1, 1));  
               cRows++;  
            }  
         }  
         else if (ptr == (SQLPOINTER)rgbRestData)  
            // varbinary(max) column.  Send data in parts.  
            for ( int i = 0 ; i < 3 ; i++ ) {  
               // Obtain the data in part from somewhere, here we just set all bytes to 'a'.  
               ::memset(rgbRestData, 'a', sizeof(rgbRestData));  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)rgbRestData, sizeof(rgbRestData)));  
            }  
         else   
            // handling other DAE parameters, but in our case, we don't have other DAE parameters.  
            goto EXIT;  
         rc = ::SQLParamData(hstmt, &ptr);  
      }  
   }  
  
   if (hstmt)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt);  
   if (hdbc) {  
      SQLDisconnect(hdbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc);  
   }  
   if (henv)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
  
EXIT:  
   if (!SUCCESS(rc)) {  
      if (hstmt)  
         PrintError(SQL_HANDLE_STMT, hstmt);  
      if (hdbc)  
         PrintError(SQL_HANDLE_DBC, hdbc);  
      if(henv)  
         PrintError(SQL_HANDLE_ENV, henv);  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="272be-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="272be-140">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="272be-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="272be-141">Description</span></span>  
 <span data-ttu-id="272be-142">In questo esempio viene illustrato come utilizzare il flusso di righe, più righe per chiamata a SQLPutData con ODBC TVP, in modo analogo a come utilizzare BCP.exe per caricare dati in un database.</span><span class="sxs-lookup"><span data-stu-id="272be-142">This sample shows that you can use row streaming, multiple rows per call to SQLPutData, with ODBC TVP, similar to how you might use BCP.exe to load data into a database.</span></span>  
  
 <span data-ttu-id="272be-143">Prima di compilare l'esempio, modificare il nome del server nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="272be-143">Before building the sample, change the server name in the connection string.</span></span>  
  
 <span data-ttu-id="272be-144">In questo esempio viene utilizzato il database predefinito.</span><span class="sxs-lookup"><span data-stu-id="272be-144">This sample uses the default database.</span></span> <span data-ttu-id="272be-145">Prima di eseguire questo esempio, eseguire i comandi seguenti nel database che verrà utilizzato:</span><span class="sxs-lookup"><span data-stu-id="272be-145">Before running this sample, run the following commands in the database you will use:</span></span>  
  
```  
create table MCLOG (  
   biSeqNo bigint,   
   iSeries int,   
   bmRestData varbinary(max)  
)  
go  
  
-- Table type definition  
create type MCLOGType   
   as table(biSeqNo bigint, iSeries int, bmRestData varbinary(max) )  
go  
  
-- Insert procedure  
create procedure MCLOGInsert (@TableVariable MCLOGType READONLY)  
   as  
   insert into MCLog(biSeqNo,  iSeries, bmRestData)   
   select biSeqNo, iSeries, bmRestData from @TableVariable    
go  
```  
  
### <a name="code"></a><span data-ttu-id="272be-146">Codice</span><span class="sxs-lookup"><span data-stu-id="272be-146">Code</span></span>  
  
```  
#define UNICODE  
#define _UNICODE  
#define _SQLNCLI_ODBC_  
  
#include <windows.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// link to sqlncli11.lib  
  
#define SUCCESS(x) ( \  
   !((x) & 0xFFFE) \  
   )  
  
#define CHKRC(stmt) { \  
   rc = (stmt); \  
   if (!SUCCESS(rc)) { \  
      _tprintf(_T(#stmt) _T(" failed with rc = %ld\r\n"), rc); \  
      goto EXIT; \  
   } \  
};  
  
void PrintError(SQLSMALLINT HandleType, SQLHANDLE Handle) {  
   RETCODE rc = SQL_SUCCESS;  
   SQLTCHAR szSqlState[6];  
   SQLTCHAR szMessage[1024];  
   SQLSMALLINT i = 1;  
   SQLSMALLINT msgLen = 0;  
   SQLINTEGER NativeError;  
  
   i = 1;  
   while ( (rc = SQLGetDiagRec(HandleType, Handle, i, szSqlState, &NativeError, szMessage, sizeof(szMessage)/sizeof(SQLTCHAR), &msgLen)) != SQL_NO_DATA) {  
      if (!SUCCESS(rc))  
         break;  
      szMessage[msgLen] = 0;  
      szSqlState[5] = 0;  
      _tprintf(_T("SQLState=%s, NativeError=%ld, Message=%s\r\n"), szSqlState, NativeError, szMessage);  
      i++;  
   }  
}  
  
int main() {  
   RETCODE rc = SQL_SUCCESS;  
   HENV henv = SQL_NULL_HENV;  
   HDBC hdbc = SQL_NULL_HDBC;  
   SQLHSTMT hstmt = SQL_NULL_HSTMT;  
   SQLTCHAR * pszConnection = _T("DRIVER={SQL Server Native Client 10.0};Server=MyServer;Trusted_Connection=Yes;");  
  
   // insert one TVP parameter  
   SQLTCHAR * pszInsertStmt = _T("{call MCLOGInsert(?)}");  
   SQLLEN cbParamLength;  
   SQLULEN cMaxRows = 9;  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HENV, &henv));  
   CHKRC(SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, 0));  
  
   CHKRC(SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc));  
   CHKRC(SQLSetConnectAttr( hdbc, SQL_ATTR_LOGIN_TIMEOUT, reinterpret_cast<SQLPOINTER>(60), SQL_IS_UINTEGER));  
   CHKRC(SQLDriverConnect( hdbc, NULL, pszConnection, SQL_NTS, NULL, 0, NULL, SQL_DRIVER_NOPROMPT));   
   CHKRC(SQLAllocHandle(SQL_HANDLE_STMT, hdbc, &hstmt));  
   CHKRC(SQLPrepare(hstmt, pszInsertStmt, SQL_NTS));  
  
   // Bind the first parameter  
   CHKRC(SQLBindParameter( hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)1, 0, &cbParamLength));  
  
   /*  
   // If the stored procedure is executed as T-SQL ("exec sp_insert ?, ?"), then, supply the type name.  
   CHKRC(SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_DEFAULT, SQL_SS_TABLE, cMaxRows, 0, (SQLPOINTER)lpszTVPParamType, SQL_NTS, &cbParamLengths));  
   */  
  
   // bind TVP columns.  
   CHKRC(SQLSetStmtAttr( hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)1, SQL_IS_INTEGER));   
  
   // For the first and the second TVP columns (bigint, int), always send them as bound.   
   // For the third column varbinary(max), either send them as bound or DAE.  
   const size_t ARRAY_SIZE = 3;  
   LONGLONG llSeqNo[ARRAY_SIZE];  
   SQLLEN cbSeqNo[ARRAY_SIZE] = {sizeof(LONGLONG), sizeof(LONGLONG), sizeof(LONGLONG)};  
   LONG lSeries[ARRAY_SIZE];  
   SQLLEN cbSeries[ARRAY_SIZE] = {sizeof(LONG), sizeof(LONG), sizeof(LONG)};  
   BYTE rgbRestData[ARRAY_SIZE][2048];  
   SQLLEN cbRestData[ARRAY_SIZE] = {sizeof(rgbRestData[0]), sizeof(rgbRestData[0]), sizeof(rgbRestData[0])};  
   SQLUSMALLINT iColumn = 1;  
  
   // Bind biSeqNo   
   CHKRC(SQLBindParameter( hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SBIGINT, SQL_BIGINT, sizeof(LONGLONG), 0, (SQLPOINTER)&llSeqNo, sizeof(llSeqNo[0]), cbSeqNo));  
  
   // Bind iSeries   
   iColumn++;  
   CHKRC(SQLBindParameter( hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_SLONG, SQL_INTEGER, sizeof(LONG), 0, (SQLPOINTER)&lSeries, sizeof(lSeries[0]), cbSeries));  
  
   // Bind bmRestData   
   iColumn++;  
   CHKRC(SQLBindParameter(hstmt, iColumn, SQL_PARAM_INPUT, SQL_C_BINARY, SQL_VARBINARY, 0, 0, (SQLPOINTER)rgbRestData, sizeof(rgbRestData[0]), cbRestData));  
  
   CHKRC(SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER)0, SQL_IS_INTEGER));  
  
   // Set cbParamLength to SQL_DATA_AT_EXEC to indicate the TVP parameter is bound as DAE.  
   cbParamLength = SQL_DATA_AT_EXEC;  
   rc = SQLExecute(hstmt);  
  
   if (rc == SQL_NEED_DATA) {  
      SQLPOINTER ptr = NULL;  
      SQLUINTEGER cRows = 0;  
  
      rc = ::SQLParamData(hstmt, &ptr);  
  
      while (rc == SQL_NEED_DATA) {  
         if (ptr == (SQLPOINTER)1) {  
            // it is the TVP parameter  
            if (cRows >= cMaxRows) {  
               // We finish sending the last row already.  
               CHKRC(::SQLPutData(hstmt, NULL, 0));  
            }  
            else {  
               // Obtaining row data from somewhere. In this case we will fill 3 rows.  
               for (size_t i = 0; i < ARRAY_SIZE; i++) {  
                  llSeqNo[i] = cRows + i + 1;  
                  lSeries[i] = llSeqNo[i] * 10;  
  
                  // Now fill the varbinary(max) column.  Assume that the even row can't be fit into   
                  // the buffer provided as send them as DAE.  
                  if (!((cRows + i) % 2)) {  
                     // SQL_DATA_AT_EXEC means send DAE data.  
                     cbRestData[i] = SQL_DATA_AT_EXEC;  
                  }  
                  else {  
                     // data can fit into the buffer, then copy the data to the buffer directly.  
                     cbRestData[i] = 100;  
                     ::memset(&rgbRestData[i], 'b', cbRestData[i]);  
                  }  
               }  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)1, ARRAY_SIZE));  
               cRows += ARRAY_SIZE;  
            }  
         }  
         else if ((SQLPOINTER)&rgbRestData[0] <= ptr && ptr <= (SQLPOINTER)&rgbRestData[ARRAY_SIZE-1]) {  
            // it is varbinary(max) column  
            // Send data in parts.  
            for (int i = 0; i < 3; i++) {  
               // Obtain the data in part from somewhere, here we just set all bytes to 'a'.  
               ::memset(ptr, 'a', sizeof(rgbRestData[0]));  
               CHKRC(::SQLPutData(hstmt, (SQLPOINTER)ptr, sizeof(rgbRestData[0])));  
            }  
         }  
         else {  
            // handling other DAE parameters, but in our case, we don't have other DAE parameters.  
            goto EXIT;  
         }  
         rc = ::SQLParamData(hstmt, &ptr);  
      }  
   }  
  
EXIT:  
   if (!SUCCESS(rc)) {  
      if (hstmt)   
         PrintError(SQL_HANDLE_STMT, hstmt);  
      if (hdbc)  
         PrintError(SQL_HANDLE_DBC, hdbc);  
      if(henv)  
         PrintError(SQL_HANDLE_ENV, henv);  
   }  
  
   if (hstmt)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt);  
   if (hdbc) {  
      SQLDisconnect(hdbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc);  
   }  
   if (henv)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="272be-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="272be-147">See Also</span></span>  
 [<span data-ttu-id="272be-148">Esempi di programmazione di parametri con valori di tabella ODBC</span><span class="sxs-lookup"><span data-stu-id="272be-148">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
  
  
