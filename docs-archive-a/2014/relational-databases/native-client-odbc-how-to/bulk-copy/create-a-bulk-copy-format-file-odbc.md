---
title: Creazione di un file di formato per la copia bulk (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC], data files
ms.assetid: 0572fef3-daf5-409e-b557-c2a632f9a06d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d35342b2f6b25a129df968383d204931d64bfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624132"
---
# <a name="create-a-bulk-copy-format-file-odbc"></a><span data-ttu-id="de9f0-102">Creare un file di formato per la copia bulk (ODBC)</span><span class="sxs-lookup"><span data-stu-id="de9f0-102">Create a Bulk Copy Format File (ODBC)</span></span>
  <span data-ttu-id="de9f0-103">In questo esempio viene illustrato come utilizzare le funzioni di copia bulk per creare un file di dati e un file di formato.</span><span class="sxs-lookup"><span data-stu-id="de9f0-103">This sample shows how to use bulk copy functions to create both a data file and a format file.</span></span> <span data-ttu-id="de9f0-104">L'esempio è stato sviluppato per ODBC versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="de9f0-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="de9f0-105">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="de9f0-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="de9f0-106">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="de9f0-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="de9f0-107">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="de9f0-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="de9f0-108">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="de9f0-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-create-a-bulk-copy-format-file"></a><span data-ttu-id="de9f0-109">Per creare un file di formato per la copia bulk</span><span class="sxs-lookup"><span data-stu-id="de9f0-109">To create a bulk copy format file</span></span>  
  
1.  <span data-ttu-id="de9f0-110">Allocare un handle di ambiente e un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="de9f0-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="de9f0-111">Impostare SQL_COPT_SS_BCP e SQL_BCP_ON in modo da abilitare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="de9f0-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="de9f0-112">Connettersi a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de9f0-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="de9f0-113">Chiamare [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) per impostare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de9f0-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="de9f0-114">Nome della tabella o della vista dalla quale o nella quale si desidera eseguire la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="de9f0-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="de9f0-115">Nome del file di dati che contiene i dati da copiare nel database o che riceve dati in caso di copia dal database.</span><span class="sxs-lookup"><span data-stu-id="de9f0-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="de9f0-116">Nome di un file di dati per la ricezione di eventuali messaggi di errore della copia bulk (specificare NULL se non si desidera che venga creato un file dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="de9f0-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="de9f0-117">Direzione della copia: DB_OUT nel file dalla tabella o dalla vista.</span><span class="sxs-lookup"><span data-stu-id="de9f0-117">The direction of the copy: DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="de9f0-118">Chiamare [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) per impostare il numero di colonne.</span><span class="sxs-lookup"><span data-stu-id="de9f0-118">Call [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to set the number of columns.</span></span>  
  
6.  <span data-ttu-id="de9f0-119">Chiamare [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) per ogni colonna per definirne le caratteristiche nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="de9f0-119">Call [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column to define its characteristics in the data file.</span></span>  
  
7.  <span data-ttu-id="de9f0-120">Chiamare [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) per creare un file di formato che descriva il file di dati che deve essere creato dall'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="de9f0-120">Call [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) to create a format file describing the data file to be created by the bulk copy operation.</span></span>  
  
8.  <span data-ttu-id="de9f0-121">Chiamare [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="de9f0-121">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="de9f0-122">L'esecuzione di un'operazione di copia bulk in questo modo determina la creazione di un file di dati che contiene i dati oggetto della copia bulk e un file di formato che descrive il layout del file di dati.</span><span class="sxs-lookup"><span data-stu-id="de9f0-122">A bulk copy operation run in this way creates both a data file containing the bulk copied data and a format file describing the layout of the data file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de9f0-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="de9f0-123">Example</span></span>  
 <span data-ttu-id="de9f0-124">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="de9f0-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="de9f0-125">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="de9f0-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="de9f0-126">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="de9f0-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="de9f0-127">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="de9f0-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="de9f0-128">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="de9f0-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="de9f0-129">Per impostazione predefinita, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="de9f0-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="de9f0-130">Eseguire il primo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per creare la tabella che verrà utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="de9f0-130">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="de9f0-131">Compilare il secondo listato di codice (C++) con odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="de9f0-131">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span>  
  
 <span data-ttu-id="de9f0-132">Eseguire il terzo listato di codice ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) per eliminare la tabella utilizzata dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="de9f0-132">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```  
use AdventureWorks  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
  
CREATE TABLE BCPDate (cola int, colb datetime)  
insert BCPDate(cola) values(1)   
insert BCPDate(cola) values(2)   
insert BCPDate(cola) values(3)   
insert BCPDate(cola) values(4)  
```  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
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
  
   // BCP variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
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
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_OUT);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the number of output columns.  
   retcode = bcp_columns(hdbc1, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 1 in the data file.  
   retcode = bcp_colfmt(hdbc1, 1, SQLCHARACTER, -1, 5, NULL, 0, 1);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 2 in the data file.  
   retcode = bcp_colfmt(hdbc1, 2, SQLCHARACTER, -1, 20, NULL, 0, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Create the format file.  
   retcode = bcp_writefmt(hdbc1, "c:\\BCPFMT.fmt");  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
   return(0);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="de9f0-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de9f0-133">See Also</span></span>  
 <span data-ttu-id="de9f0-134">[Procedure per la copia bulk con il driver ODBC di SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="de9f0-134">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="de9f0-135">Utilizzo di file di dati e file di formato</span><span class="sxs-lookup"><span data-stu-id="de9f0-135">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
