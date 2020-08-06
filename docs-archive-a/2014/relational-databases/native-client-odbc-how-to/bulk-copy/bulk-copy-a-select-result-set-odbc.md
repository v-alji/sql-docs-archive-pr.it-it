---
title: Eseguire la copia bulk di un set di risultati SELECT (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 63d5a87b-4d5f-449b-8c77-9f9cc6b190d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 6476d603a61b9dee0a8a71cb3ec1fa865d1156f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725680"
---
# <a name="bulk-copy-a-select-result-set-odbc"></a><span data-ttu-id="a1dac-102">Eseguire una copia bulk di un set di risultati SELECT (ODBC)</span><span class="sxs-lookup"><span data-stu-id="a1dac-102">Bulk Copy a SELECT Result Set (ODBC)</span></span>
  <span data-ttu-id="a1dac-103">Nell'esempio viene illustrato come utilizzare le funzioni di copia bulk per eseguire la copia bulk del set di risultati di un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="a1dac-103">This sample shows how to use bulk copy functions to bulk copy out the result set of a SELECT statement.</span></span> <span data-ttu-id="a1dac-104">L'esempio è stato sviluppato per ODBC versione 3.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a1dac-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1dac-105">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a1dac-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="a1dac-106">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1dac-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="a1dac-107">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="a1dac-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="a1dac-108">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="a1dac-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-bulk-copy-out-the-result-set-of-a-select-statement"></a><span data-ttu-id="a1dac-109">Per eseguire la copia bulk per l'esportazione del set di risultati di un'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="a1dac-109">To bulk copy out the result set of a SELECT statement</span></span>  
  
1.  <span data-ttu-id="a1dac-110">Allocare un handle di ambiente e un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="a1dac-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="a1dac-111">Impostare SQL_COPT_SS_BCP e SQL_BCP_ON in modo da abilitare le operazioni di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="a1dac-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="a1dac-112">Connettersi a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1dac-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="a1dac-113">Chiamare [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) per impostare le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1dac-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="a1dac-114">Specificare NULL per il parametro *szTable* .</span><span class="sxs-lookup"><span data-stu-id="a1dac-114">Specify NULL for the *szTable* parameter.</span></span>  
  
    -   <span data-ttu-id="a1dac-115">Nome del file di dati mediante il quale si ricevono i dati del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a1dac-115">The name of the data file that receives result set data.</span></span>  
  
    -   <span data-ttu-id="a1dac-116">Nome di un file di dati per la ricezione di eventuali messaggi di errore della copia bulk (specificare NULL se non si desidera che venga creato un file dei messaggi).</span><span class="sxs-lookup"><span data-stu-id="a1dac-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="a1dac-117">Direzione della copia: DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="a1dac-117">The direction of the copy: DB_OUT.</span></span>  
  
5.  <span data-ttu-id="a1dac-118">Chiamare [bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md), impostare EOPTION su BCPHINTS e inserire in iValue un puntatore a una matrice SQLTCHAR che contiene l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="a1dac-118">Call [bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md), set eOption to BCPHINTS and place in iValue a pointer to a SQLTCHAR array containing the SELECT statement.</span></span>  
  
6.  <span data-ttu-id="a1dac-119">Chiamare [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) per eseguire l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="a1dac-119">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="a1dac-120">Quando vengono seguiti questi passaggi, il file viene creato in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="a1dac-120">When using these steps the file is created in native format.</span></span> <span data-ttu-id="a1dac-121">È possibile convertire i valori dei dati in altri tipi di dati utilizzando [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="a1dac-121">You can convert the data values to other data types by using [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md).</span></span> <span data-ttu-id="a1dac-122">Per ulteriori informazioni, vedere [creare un file di formato per la copia Bulk &#40;&#41;ODBC ](create-a-bulk-copy-format-file-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a1dac-122">For more information, see [Create a Bulk Copy Format File &#40;ODBC&#41;](create-a-bulk-copy-format-file-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1dac-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1dac-123">Example</span></span>  
 <span data-ttu-id="a1dac-124">È necessaria un'origine dati ODBC denominata AdventureWorks, il cui database predefinito è il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a1dac-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="a1dac-125">È possibile scaricare il database di esempio AdventureWorks dal [Microsoft SQL Server esempi e progetti della Community](https://go.microsoft.com/fwlink/?LinkID=85384) Home page. Questa origine dati deve essere basata sul driver ODBC fornito dal sistema operativo (il nome del driver è "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="a1dac-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="a1dac-126">Se questo esempio viene compilato ed eseguito come applicazione a 32 bit in un sistema operativo a 64 bit, è necessario creare l'origine dati ODBC con Amministratore ODBC in %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="a1dac-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="a1dac-127">In questo esempio viene eseguita la connessione all'istanza predefinita di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="a1dac-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="a1dac-128">Per connettersi a un'istanza denominata, modificare la definizione dell'origine dati ODBC per specificare l'istanza in base al formato: server\istanzadenominata.</span><span class="sxs-lookup"><span data-stu-id="a1dac-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="a1dac-129">Per impostazione predefinita, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] viene installato in un'istanza denominata.</span><span class="sxs-lookup"><span data-stu-id="a1dac-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="a1dac-130">Eseguire la compilazione con odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="a1dac-130">Compile with odbc32.lib and odbcbcp.lib.</span></span>  
  
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
   SQLTCHAR szBCPQuery[] = "SELECT BirthDate FROM HumanResources.Employee";  
  
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
  
   // Sample use Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, NULL, "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // The test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Specify the query to use.  
   retcode = bcp_control(hdbc1, BCPHINTS, (void *)szBCPQuery);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_control(hdbc1) Failed\n\n");  
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
  
## <a name="see-also"></a><span data-ttu-id="a1dac-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1dac-131">See Also</span></span>  
 [<span data-ttu-id="a1dac-132">Procedure per la copia bulk con il driver ODBC di SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="a1dac-132">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  
