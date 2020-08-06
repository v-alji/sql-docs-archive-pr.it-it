---
title: Eseguire una copia bulk senza un file di formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 4ee969a7-44ba-40d0-b9ab-8306f1a2b19d
author: rothja
ms.author: jroth
ms.openlocfilehash: a65f013d92f5a5d39a580cfb3a9bd77bc6f84e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725668"
---
# <a name="bulk-copy-without-a-format-file-odbc"></a><span data-ttu-id="71a91-102">Eseguire una copia bulk senza un file di formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="71a91-102">Bulk Copy Without a Format File (ODBC)</span></span>
  <span data-ttu-id="71a91-103">In questo esempio viene illustrato come utilizzare le funzioni di copia bulk per creare un file di dati in modalità nativa senza un file di formato.</span><span class="sxs-lookup"><span data-stu-id="71a91-103">This sample shows how to use bulk copy functions to create a native mode data file, without a format file.</span></span> <span data-ttu-id="71a91-104">L'esempio è stato sviluppato per ODBC versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="71a91-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="71a91-105">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="71a91-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="71a91-106">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="71a91-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="71a91-107">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="71a91-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="71a91-108">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="71a91-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-bulk-copy-without-a-format-file"></a><span data-ttu-id="71a91-109">Per eseguire la copia bulk senza un file di formato</span><span class="sxs-lookup"><span data-stu-id="71a91-109">To bulk copy without a format file</span></span>  
  
1.  <span data-ttu-id="71a91-110">Allocare un handle di ambiente e un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="71a91-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="71a91-111">Impostare SQL_COPT_SS_BCP e SQL_BCP_ON in modo da abilitare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="71a91-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="71a91-112">Connettersi a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="71a91-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="71a91-113">Chiamare [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) per impostare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="71a91-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="71a91-114">Nome della tabella o della vista dalla quale o nella quale si desidera eseguire la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="71a91-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="71a91-115">Nome del file di dati che contiene i dati da copiare nel database o che riceve dati in caso di copia dal database.</span><span class="sxs-lookup"><span data-stu-id="71a91-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="71a91-116">Nome di un file di dati per la ricezione di eventuali messaggi di errore della copia bulk (specificare NULL se non si desidera che venga creato un file dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="71a91-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="71a91-117">Direzione della copia: DB_IN dal file alla tabella o alla vista, DB_OUT dalla tabella o dalla vista al file.</span><span class="sxs-lookup"><span data-stu-id="71a91-117">The direction of the copy: DB_IN from the file to the view or table, or DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="71a91-118">Chiamare [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="71a91-118">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="71a91-119">Quando DB_OUT viene impostato con questi passaggi, il file viene creato in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="71a91-119">When DB_OUT is set with these steps, the file is created in native format.</span></span> <span data-ttu-id="71a91-120">È quindi possibile eseguire la copia bulk del file in un server utilizzando questi stessi passaggi, con la differenza che viene impostato DB_OUT anziché DB_IN.</span><span class="sxs-lookup"><span data-stu-id="71a91-120">The file can then be bulk copied into a server by following these same steps, except that DB_OUT is set instead of DB_IN.</span></span> <span data-ttu-id="71a91-121">È possibile procedere in questo modo solo se le tabelle di origine e di destinazione hanno una struttura identica.</span><span class="sxs-lookup"><span data-stu-id="71a91-121">This works only if both the source and target tables have exactly the same structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a91-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="71a91-122">Example</span></span>  
 <span data-ttu-id="71a91-123">Questo esempio non è supportato in IA64.</span><span class="sxs-lookup"><span data-stu-id="71a91-123">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="71a91-124">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="71a91-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="71a91-125">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="71a91-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="71a91-126">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="71a91-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="71a91-127">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="71a91-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="71a91-128">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="71a91-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="71a91-129">Per impostazione predefinita, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="71a91-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="71a91-130">Eseguire la compilazione con odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="71a91-130">Compile with odbc32.lib and odbcbcp.lib.</span></span>  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
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
  
   // Bulk copy variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and then connect.  
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
  
   // Sample uses Integrated Security, create the SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "Purchasing.Vendor", "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // Test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
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
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="71a91-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71a91-131">See Also</span></span>  
 [<span data-ttu-id="71a91-132">Procedure per la copia bulk con il driver ODBC di SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="71a91-132">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  
