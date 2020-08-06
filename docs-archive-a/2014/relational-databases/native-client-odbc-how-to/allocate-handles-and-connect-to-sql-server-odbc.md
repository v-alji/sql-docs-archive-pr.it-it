---
title: Allocare handle e connettersi a SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725684"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="3c0e1-102">Allocare handle e connettersi a SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3c0e1-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="3c0e1-103">Per allocare handle e connettersi a SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c0e1-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="3c0e1-104">Includere i file di intestazione ODBC Sql.h, Sqlext.h, Sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="3c0e1-105">Includere il file di intestazione specifico del driver [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="3c0e1-106">Chiamare [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` di SQL_HANDLE_ENV per inizializzare ODBC e allocare un handle di ambiente.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="3c0e1-107">Chiamare [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) con `Attribute` impostato su SQL_ATTR_ODBC_VERSION e `ValuePtr` impostato su SQL_OV_ODBC3 per indicare che l'applicazione utilizzerà le chiamate di funzione ODBC 3. x format.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="3c0e1-108">Facoltativamente, chiamare [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) per impostare altre opzioni di ambiente o chiamare [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) per ottenere le opzioni di ambiente.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="3c0e1-109">Chiamare [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` di SQL_HANDLE_DBC per allocare un handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="3c0e1-110">Facoltativamente, chiamare [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) per impostare le opzioni di connessione oppure chiamare [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) per ottenere le opzioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="3c0e1-111">Chiamare SQLConnect per utilizzare un'origine dati esistente a cui connettersi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c0e1-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="3c0e1-112">Oppure</span><span class="sxs-lookup"><span data-stu-id="3c0e1-112">Or</span></span>  
  
     <span data-ttu-id="3c0e1-113">Chiamare [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) per usare una stringa di connessione per la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c0e1-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="3c0e1-114">Il formato minimo di una stringa di connessione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] completa può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c0e1-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="3c0e1-115">Se la stringa di connessione non è completa, `SQLDriverConnect` può richiedere le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="3c0e1-116">Questa operazione è controllata dal valore specificato per il parametro *DriverCompletion* .</span><span class="sxs-lookup"><span data-stu-id="3c0e1-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="3c0e1-117">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="3c0e1-117">\- or -</span></span>  
  
     <span data-ttu-id="3c0e1-118">Chiamare [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) più volte in modo iterativo per compilare la stringa di connessione e connettersi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c0e1-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="3c0e1-119">Facoltativamente, chiamare [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) per ottenere gli attributi e il comportamento del driver per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origine dati.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="3c0e1-120">Allocare e utilizzare le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="3c0e1-121">Chiamare Disconnect per disconnettersi da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e rendere disponibile l'handle di connessione per una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="3c0e1-122">Chiamare [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) con un `HandleType` di SQL_HANDLE_DBC per liberare l'handle di connessione.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="3c0e1-123">Chiamare `SQLFreeHandle` con `HandleType` impostato su SQL_HANDLE_ENV per liberare l'handle di ambiente.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c0e1-124">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="3c0e1-125">Se non è disponibile, agli utenti verrà richiesto di immettere le credenziali in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="3c0e1-126">Evitare di archiviare le credenziali in un file.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="3c0e1-127">Se è necessario salvare in modo permanente le credenziali, è necessario crittografarle con l' [API di crittografia Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="3c0e1-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c0e1-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="3c0e1-128">Example</span></span>  
 <span data-ttu-id="3c0e1-129">In questo esempio viene mostrata una chiamata a `SQLDriverConnect` per connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senza richiedere un'origine dati ODBC esistente.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="3c0e1-130">Passando una stringa di connessione incompleta a `SQLDriverConnect`, fa in modo che il driver ODBC richieda all'utente di immettere le informazioni mancanti.</span><span class="sxs-lookup"><span data-stu-id="3c0e1-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
