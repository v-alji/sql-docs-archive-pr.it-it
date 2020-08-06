---
title: Utilizzare le colonne data-at-execution (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 4eae58d1-03d4-40ca-8aa1-9b3ea10a38cf
author: rothja
ms.author: jroth
ms.openlocfilehash: 68690208b690f94909100132c966eb59d11e4652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722772"
---
# <a name="use-data-at-execution-columns-odbc"></a><span data-ttu-id="6d90c-102">Utilizzare colonne data-at-execution (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6d90c-102">Use Data-at-Execution Columns (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-columns"></a><span data-ttu-id="6d90c-103">Per utilizzare le colonne data-at-execution di tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="6d90c-103">To use data-at-execution text, ntext, or image columns</span></span>  
  
1.  <span data-ttu-id="6d90c-104">Per ogni colonna data-at-execution, inserire valori speciali nei buffer precedentemente associati da [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span><span class="sxs-lookup"><span data-stu-id="6d90c-104">For each data-at-execution column, put special values into the buffers previously bound by [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span></span>  
  
    -   <span data-ttu-id="6d90c-105">Per l'ultimo parametro, utilizzare SQL_LEN_DATA_AT_EXEC(length), dove length è la lunghezza totale, espressa in byte, dei dati della colonna di tipo text, ntext o image.</span><span class="sxs-lookup"><span data-stu-id="6d90c-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(length) where length is the total length of the text, ntext, or image column data in bytes.</span></span>  
  
    -   <span data-ttu-id="6d90c-106">Per il quarto parametro, inserire un identificatore della colonna definito dal programma.</span><span class="sxs-lookup"><span data-stu-id="6d90c-106">For the fourth parameter, put a program-defined column identifier.</span></span>  
  
2.  <span data-ttu-id="6d90c-107">Se si chiama [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407), viene restituito SQL_NEED_DATA, che indica che le colonne data-at-execution sono pronte per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="6d90c-107">Calling [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) returns SQL_NEED_DATA, which indicates that data-at-execution columns are ready for processing.</span></span>  
  
3.  <span data-ttu-id="6d90c-108">Per ogni colonna data-at-execution:</span><span class="sxs-lookup"><span data-stu-id="6d90c-108">For each data-at-execution column:</span></span>  
  
    -   <span data-ttu-id="6d90c-109">Chiamare [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) per ottenere il puntatore di una matrice di colonna.</span><span class="sxs-lookup"><span data-stu-id="6d90c-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the column array pointer.</span></span> <span data-ttu-id="6d90c-110">Verrà restituito SQL_NEED_DATA se è presente un'altra colonna data-at-execution.</span><span class="sxs-lookup"><span data-stu-id="6d90c-110">It will return SQL_NEED_DATA if there is another data-at-execution column.</span></span>  
  
    -   <span data-ttu-id="6d90c-111">Chiamare [SQLPutData](../native-client-odbc-api/sqlputdata.md) una o più volte per inviare i dati della colonna, fino quando non viene inviata la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="6d90c-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times to send the column data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="6d90c-112">Chiamare [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) per indicare che tutti i dati relativi alla colonna data-at-execution finale devono essere inviati.</span><span class="sxs-lookup"><span data-stu-id="6d90c-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution column is sent.</span></span> <span data-ttu-id="6d90c-113">Non verrà restituito SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="6d90c-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d90c-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d90c-114">Example</span></span>  
 <span data-ttu-id="6d90c-115">In questo esempio viene illustrato come leggere dati di tipo carattere variabili SQL_LONG mediante SQLGetData.</span><span class="sxs-lookup"><span data-stu-id="6d90c-115">The sample shows how to read a SQL_LONG variable character data using SQLGetData.</span></span> <span data-ttu-id="6d90c-116">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="6d90c-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="6d90c-117">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6d90c-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="6d90c-118">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="6d90c-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="6d90c-119">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="6d90c-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="6d90c-120">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="6d90c-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="6d90c-121">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="6d90c-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="6d90c-122">Per impostazione predefinita, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="6d90c-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="6d90c-123">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per creare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6d90c-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="6d90c-124">Compilare il secondo listato di codice (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="6d90c-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="6d90c-125">Eseguire quindi il programma.</span><span class="sxs-lookup"><span data-stu-id="6d90c-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="6d90c-126">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../includes/tsql-md.md)]) per eliminare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6d90c-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp3 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name1', '12', 'This is the first employee')  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name2', '18', 'This is the second employee')  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define BUFFERSIZE  450  
  
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
};  
  
int main() {  
   RETCODE retcode;  
   SWORD cntr;  
  
   // SQLGetData variables.  
   UCHAR Data[BUFFERSIZE];  
   SDWORD cbBatch = (SDWORD)sizeof(Data)-1;  
   SQLLEN cbTxtSize;  
  
   // Clear data array.  
   for (cntr = 0 ; cntr < BUFFERSIZE ; cntr++)  
      Data[cntr] = 0x00;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle; prepare, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT Memo1 FROM emp3", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get first row.  
   retcode = SQLFetch(hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLFetch(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get the SQL_LONG column.  
   cntr = 1;  
   while ( (retcode = SQLGetData(hstmt1, 1, SQL_C_CHAR, Data, cbBatch, &cbTxtSize)) != SQL_NO_DATA) {  
      printf("GetData iteration %d, pcbValue = %d,\n", cntr++, cbTxtSize);  
      printf("Data = %s\n\n", Data);  
  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("GetData(hstmt1) Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }   
  
   // Clean up  
   //SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp3')  
     DROP TABLE emp3  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d90c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d90c-127">See Also</span></span>  
 [<span data-ttu-id="6d90c-128">Procedure per la gestione di colonne di testo e di immagini &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="6d90c-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
