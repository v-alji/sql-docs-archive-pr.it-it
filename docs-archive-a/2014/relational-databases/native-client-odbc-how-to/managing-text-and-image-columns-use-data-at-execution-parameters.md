---
title: Usare i parametri data-at-execution (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 2a738aef-c991-4f62-bdab-a5221c335f31
author: rothja
ms.author: jroth
ms.openlocfilehash: cf87309f1e325b94ff455d446fbd2e76d5c06ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722768"
---
# <a name="use-data-at-execution-parameters-odbc"></a><span data-ttu-id="c3fef-102">Utilizzare parametri data-at-execution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c3fef-102">Use Data-at-Execution Parameters (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-parameters"></a><span data-ttu-id="c3fef-103">Per utilizzare i parametri data-at-execution di tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="c3fef-103">To use data-at-execution text, ntext, or image parameters</span></span>  
  
1.  <span data-ttu-id="c3fef-104">Durante la chiamata a [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) per associare un buffer del programma al parametro dell'istruzione:</span><span class="sxs-lookup"><span data-stu-id="c3fef-104">When calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind a program buffer to the statement parameter:</span></span>  
  
    -   <span data-ttu-id="c3fef-105">Per l'ultimo parametro, utilizzare SQL_LEN_DATA_AT_EXEC (*length*), dove *length* è la lunghezza totale `text` , `ntext` in byte, dei dati del parametro, o `image` .</span><span class="sxs-lookup"><span data-stu-id="c3fef-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(*length*) where *length* is the total length of the `text`, `ntext`, or `image` parameter data in bytes.</span></span>  
  
    -   <span data-ttu-id="c3fef-106">Utilizzare un `rgbValue` (ottavo parametro) di un identificatore di parametro definito dal programma.</span><span class="sxs-lookup"><span data-stu-id="c3fef-106">Use an `rgbValue` (eighth parameter) of a program-defined parameter identifier.</span></span>  
  
2.  <span data-ttu-id="c3fef-107">La chiamata di [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) o [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) restituisce SQL_NEED_DATA, che indica che i parametri data-at-execution sono pronti per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="c3fef-107">Calling [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) or [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA, which indicates that data-at-execution parameters are ready for processing.</span></span>  
  
3.  <span data-ttu-id="c3fef-108">Per ogni parametro data-at-execution:</span><span class="sxs-lookup"><span data-stu-id="c3fef-108">For each data-at-execution parameter:</span></span>  
  
    -   <span data-ttu-id="c3fef-109">Chiamare [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) per ottenere l'ID del parametro definito dal programma.</span><span class="sxs-lookup"><span data-stu-id="c3fef-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the program-defined parameter ID.</span></span> <span data-ttu-id="c3fef-110">Se è presente un altro parametro data-at-execution, verrà restituito SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c3fef-110">It will return SQL_NEED_DATA if there is another data-at-execution parameter.</span></span>  
  
    -   <span data-ttu-id="c3fef-111">Chiamare [SQLPutData](../native-client-odbc-api/sqlputdata.md) una o più volte per inviare i dati del parametro, fino a quando non viene inviata la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="c3fef-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times, to send the parameter data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="c3fef-112">Chiamare [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) per indicare che tutti i dati relativi al parametro data-at-execution finale vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="c3fef-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution parameter is sent.</span></span> <span data-ttu-id="c3fef-113">Non verrà restituito SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="c3fef-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3fef-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3fef-114">Example</span></span>  
 <span data-ttu-id="c3fef-115">In questo esempio viene illustrato come leggere dati di tipo carattere variabili SQL_LONG mediante SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="c3fef-115">The sample shows how to read SQL_LONG variable character data using SQLParamData and SQLPutData.</span></span> <span data-ttu-id="c3fef-116">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="c3fef-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="c3fef-117">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="c3fef-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="c3fef-118">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="c3fef-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="c3fef-119">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="c3fef-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="c3fef-120">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="c3fef-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="c3fef-121">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="c3fef-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="c3fef-122">Per impostazione predefinita, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="c3fef-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="c3fef-123">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per creare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="c3fef-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="c3fef-124">Compilare il secondo listato di codice (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="c3fef-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="c3fef-125">Eseguire quindi il programma.</span><span class="sxs-lookup"><span data-stu-id="c3fef-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="c3fef-126">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per eliminare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="c3fef-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp4 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define TEXTSIZE  12000  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // SQLBindParameter variables.  
   SQLLEN cbTextSize, lbytes;  
  
   // SQLParamData variable.  
   PTR pParmID;  
  
   // SQLPutData variables.  
   UCHAR  Data[] =   
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyz";  
  
   SDWORD cbBatch = (SDWORD)sizeof(Data) - 1;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set parameters based on total data to send.  
   lbytes = (SDWORD)TEXTSIZE;  
   cbTextSize = SQL_LEN_DATA_AT_EXEC(lbytes);  
  
   // Bind the parameter marker.  
   retcode = SQLBindParameter (hstmt1,           // hstmt  
                               1,                // ipar  
                               SQL_PARAM_INPUT,  // fParamType  
                               SQL_C_CHAR,       // fCType  
                               SQL_LONGVARCHAR,  // FSqlType  
                               lbytes,           // cbColDef  
                               0,                // ibScale  
                               (VOID *)1,        // rgbValue  
                               0,                // cbValueMax  
                               &cbTextSize);     // pcbValue  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the command.  
   retcode =   
      SQLExecDirect(hstmt1, (UCHAR*)"INSERT INTO emp4 VALUES('Paul Borm', 46,'1950-11-12 00:00:00', ?)", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_NEED_DATA) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Check to see if NEED_DATA; if yes, use SQLPutData.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if (retcode == SQL_NEED_DATA) {  
      while (lbytes > cbBatch) {  
         SQLPutData(hstmt1, Data, cbBatch);  
         lbytes -= cbBatch;  
      }  
      // Put final batch.  
      retcode = SQLPutData(hstmt1, Data, lbytes);   
   }  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Make final SQLParamData call.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("Final SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clean up.  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp4')  
     DROP TABLE emp4  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3fef-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3fef-127">See Also</span></span>  
 [<span data-ttu-id="c3fef-128">Procedure per la gestione di colonne di testo e di immagini &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c3fef-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
