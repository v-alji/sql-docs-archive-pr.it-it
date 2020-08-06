---
title: Eseguire una copia bulk utilizzando un file di formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725679"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="6aae4-102">Eseguire una copia bulk utilizzando un file di formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="6aae4-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="6aae4-103">In questo esempio viene illustrato come utilizzare la funzione ODBC bcp_init con un file di formato.</span><span class="sxs-lookup"><span data-stu-id="6aae4-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="6aae4-104">Per eseguire una copia bulk utilizzando un file di formato</span><span class="sxs-lookup"><span data-stu-id="6aae4-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="6aae4-105">Allocare un handle di ambiente e un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="6aae4-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="6aae4-106">Impostare SQL_COPT_SS_BCP e SQL_BCP_ON in modo da abilitare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="6aae4-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="6aae4-107">Connettersi a Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6aae4-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="6aae4-108">Chiamare [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) per impostare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6aae4-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="6aae4-109">Nome della tabella o della vista dalla quale o nella quale si desidera eseguire la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="6aae4-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="6aae4-110">Nome del file di dati che contiene i dati da copiare nel database o che riceve dati in caso di copia dal database.</span><span class="sxs-lookup"><span data-stu-id="6aae4-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="6aae4-111">Nome di un file di dati per la ricezione di eventuali messaggi di errore della copia bulk (specificare NULL se non si desidera che venga creato un file dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="6aae4-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="6aae4-112">Direzione della copia: DB_IN dal file alla tabella o alla vista.</span><span class="sxs-lookup"><span data-stu-id="6aae4-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="6aae4-113">Chiamare [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) per leggere il file di formato che descrive il file di dati che deve essere utilizzato dall'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="6aae4-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="6aae4-114">Chiamare [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="6aae4-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aae4-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="6aae4-115">Example</span></span>  
 <span data-ttu-id="6aae4-116">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="6aae4-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="6aae4-117">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="6aae4-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="6aae4-118">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="6aae4-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="6aae4-119">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="6aae4-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="6aae4-120">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="6aae4-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="6aae4-121">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="6aae4-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="6aae4-122">Per impostazione predefinita, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="6aae4-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="6aae4-123">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per creare la tabella che verrà utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6aae4-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="6aae4-124">Copiare il secondo listato di codice e incollarlo in un file denominato Bcpfmt.fmt.</span><span class="sxs-lookup"><span data-stu-id="6aae4-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="6aae4-125">Ogni colonna nella tabella è separata da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="6aae4-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="6aae4-126">Copiare il terzo listato di codice e incollarlo in un file denominato Bcpodbc.bcp.</span><span class="sxs-lookup"><span data-stu-id="6aae4-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="6aae4-127">Ogni ritorno a capo nel file è preceduto da un carattere di tabulazione.</span><span class="sxs-lookup"><span data-stu-id="6aae4-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="6aae4-128">Compilare il quarto listato di codice (C++) con odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="6aae4-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="6aae4-129">Se è stata eseguita la compilazione con MSBuild.exe, copiare Bcpfmt.fmt e Bcpodbc.bcp dalla directory del progetto in quella contenente il file con estensione exe e quindi richiamare tale file.</span><span class="sxs-lookup"><span data-stu-id="6aae4-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="6aae4-130">Eseguire il quinto listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per eliminare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="6aae4-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6aae4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aae4-131">See Also</span></span>  
 <span data-ttu-id="6aae4-132">[Procedure per la copia bulk con il driver ODBC di SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="6aae4-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="6aae4-133">Utilizzo di file di dati e file di formato</span><span class="sxs-lookup"><span data-stu-id="6aae4-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
