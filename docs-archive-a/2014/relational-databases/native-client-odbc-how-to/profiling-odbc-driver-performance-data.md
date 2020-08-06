---
title: Dati sulle prestazioni del driver del profilo (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714328"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="64c65-102">Analizzare i dati relativi alle prestazioni del driver (ODBC)</span><span class="sxs-lookup"><span data-stu-id="64c65-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="64c65-103">In questo esempio vengono illustrate le opzioni specifiche del driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la registrazione delle statistiche relative alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="64c65-104">Nell'esempio viene creato il file odbcperf.log e vengono illustrate sia la creazione di un file di log dei dati relativi alle prestazioni che la visualizzazione dei dati relativi alle prestazioni direttamente dalla struttura di dati SQLPERF, definita in Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="64c65-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="64c65-105">L'esempio è stato sviluppato per ODBC versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="64c65-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="64c65-106">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="64c65-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="64c65-107">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64c65-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="64c65-108">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="64c65-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="64c65-109">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="64c65-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="64c65-110">Per registrare i dati relativi alle prestazioni del driver tramite Amministratore ODBC</span><span class="sxs-lookup"><span data-stu-id="64c65-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="64c65-111">Nel **Pannello di controllo**fare doppio clic su **strumenti di amministrazione** , quindi fare doppio clic su **origini dati (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="64c65-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="64c65-112">In alternativa, è possibile richiamare odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="64c65-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="64c65-113">Fare clic sulla scheda DSN **utente**, **DSN di sistema**o **DSN su file** .</span><span class="sxs-lookup"><span data-stu-id="64c65-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="64c65-114">Fare clic sull'origine dati per cui registrare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="64c65-115">Fare clic su **Configura**.</span><span class="sxs-lookup"><span data-stu-id="64c65-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="64c65-116">Nella procedura guidata Microsoft SQL Server configurazione DSN, passare alla pagina contenente **le statistiche del driver ODBC di log nel file di log**.</span><span class="sxs-lookup"><span data-stu-id="64c65-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="64c65-117">Selezionare **registra statistiche driver ODBC nel file di log**.</span><span class="sxs-lookup"><span data-stu-id="64c65-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="64c65-118">Nella casella immettere il nome del file in cui si desidera salvare le statistiche.</span><span class="sxs-lookup"><span data-stu-id="64c65-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="64c65-119">Facoltativamente, fare clic su **Sfoglia** per visualizzare il file System per il registro delle statistiche.</span><span class="sxs-lookup"><span data-stu-id="64c65-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="64c65-120">Per registrare i dati relativi alle prestazioni del driver a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="64c65-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="64c65-121">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA_LOG e il percorso completo e il nome file del file di log dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="64c65-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="64c65-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="64c65-123">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA e SQL_PERF_START per avviare la registrazione dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="64c65-124">Facoltativamente, chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_LOG_NOW e null per scrivere un record delimitato da tabulazioni dei dati sulle prestazioni nel file di log dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="64c65-125">Questa operazione può essere eseguita più volte durante l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64c65-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="64c65-126">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA e SQL_PERF_STOP per arrestare la registrazione dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="64c65-127">Per estrarre i dati relativi alle prestazioni in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="64c65-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="64c65-128">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA e SQL_PERF_START per avviare la profilatura dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="64c65-129">Chiamare [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) con SQL_COPT_SS_PERF_DATA e l'indirizzo di un puntatore a una struttura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="64c65-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="64c65-130">La prima di tali chiamate imposta il puntatore sull'indirizzo di una struttura SQLPERF valida che contiene i dati relativi alle prestazioni correnti.</span><span class="sxs-lookup"><span data-stu-id="64c65-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="64c65-131">Il driver non aggiorna continuamente i dati nella struttura delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="64c65-132">L'applicazione deve ripetere la chiamata a [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) ogni volta che è necessario aggiornare la struttura con dati sulle prestazioni più recenti.</span><span class="sxs-lookup"><span data-stu-id="64c65-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="64c65-133">Chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA e SQL_PERF_STOP per arrestare la registrazione dei dati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="64c65-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64c65-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="64c65-134">Example</span></span>  
 <span data-ttu-id="64c65-135">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="64c65-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="64c65-136">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="64c65-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="64c65-137">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="64c65-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="64c65-138">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="64c65-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="64c65-139">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="64c65-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="64c65-140">Per impostazione predefinita, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="64c65-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="64c65-141">Eseguire la compilazione con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="64c65-141">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
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
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="64c65-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64c65-142">See Also</span></span>  
 <span data-ttu-id="64c65-143">[Procedure per la profilatura delle prestazioni del driver ODBC &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="64c65-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="64c65-144">Profiling delle prestazioni del driver ODBC</span><span class="sxs-lookup"><span data-stu-id="64c65-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
