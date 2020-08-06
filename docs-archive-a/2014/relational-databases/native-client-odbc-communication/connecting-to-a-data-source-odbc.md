---
title: Connessione a un'origine dati (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628650"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="5a97b-102">Connessione a un'origine dati (ODBC)</span><span class="sxs-lookup"><span data-stu-id="5a97b-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="5a97b-103">Dopo avere allocato handle di ambiente e di connessione e avere impostato tutti gli attributi di connessione, l'applicazione si connette all'origine dati o al driver.</span><span class="sxs-lookup"><span data-stu-id="5a97b-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="5a97b-104">È possibile utilizzare tre funzioni per connettersi:</span><span class="sxs-lookup"><span data-stu-id="5a97b-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="5a97b-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="5a97b-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="5a97b-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="5a97b-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="5a97b-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="5a97b-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="5a97b-108">Per ulteriori informazioni sull'esecuzione di connessioni a un'origine dati, incluse le varie opzioni della stringa di connessione disponibili, vedere [utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="5a97b-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="5a97b-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="5a97b-109">SQLConnect</span></span>  
 <span data-ttu-id="5a97b-110">**SQLConnect** è la funzione di connessione più semplice.</span><span class="sxs-lookup"><span data-stu-id="5a97b-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="5a97b-111">La funzione accetta tre parametri: un nome di origine dati, un ID utente e una password.</span><span class="sxs-lookup"><span data-stu-id="5a97b-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="5a97b-112">Utilizzare **SQLConnect** quando questi tre parametri contengono tutte le informazioni necessarie per connettersi al database.</span><span class="sxs-lookup"><span data-stu-id="5a97b-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="5a97b-113">A tale scopo, compilare un elenco di origini dati utilizzando **SQLDataSources**; Richiedi all'utente un'origine dati, un ID utente e una password. e quindi chiamare **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="5a97b-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="5a97b-114">**SQLConnect** presuppone che il nome dell'origine dati, l'ID utente e la password siano sufficienti per connettersi a un'origine dati e che l'origine dati ODBC contenga tutte le altre informazioni necessarie al driver ODBC per stabilire la connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="5a97b-115">A differenza di [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) e [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** non usa una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="5a97b-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="5a97b-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="5a97b-117">**SQLDriverConnect** viene utilizzato quando sono necessarie più informazioni rispetto al nome dell'origine dati, all'ID utente e alla password.</span><span class="sxs-lookup"><span data-stu-id="5a97b-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="5a97b-118">Uno dei parametri di **SQLDriverConnect** è una stringa di connessione contenente informazioni specifiche del driver.</span><span class="sxs-lookup"><span data-stu-id="5a97b-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="5a97b-119">È possibile utilizzare **SQLDriverConnect** anziché **SQLConnect** per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a97b-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="5a97b-120">Per immettere informazioni specifiche del driver in fase di connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="5a97b-121">Per specificare che il driver deve richiedere all'utente le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="5a97b-122">Per connettersi senza utilizzare un'origine dati ODBC.</span><span class="sxs-lookup"><span data-stu-id="5a97b-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="5a97b-123">La stringa di connessione **SQLDriverConnect** contiene una serie di coppie parola chiave-valore che specificano tutte le informazioni di connessione supportate da un driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="5a97b-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="5a97b-124">Ogni driver supporta le parole chiave ODBC standard (DSN, FILEDSN, DRIVER, UID, PWD e SAVEFILE) oltre a parole chiave specifiche del driver per tutte le informazioni di connessione supportate dal driver stesso.</span><span class="sxs-lookup"><span data-stu-id="5a97b-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="5a97b-125">**SQLDriverConnect** può essere usato per connettersi senza un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="5a97b-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="5a97b-126">Ad esempio, un'applicazione progettata per effettuare una connessione "senza DSN" a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] può chiamare **SQLDriverConnect** con una stringa di connessione che definisce l'ID di accesso, la password, la libreria di rete, il nome del server a cui connettersi e il database predefinito da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5a97b-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="5a97b-127">Quando si usa **SQLDriverConnect**, sono disponibili due opzioni per richiedere all'utente le informazioni di connessione necessarie:</span><span class="sxs-lookup"><span data-stu-id="5a97b-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="5a97b-128">Finestra di dialogo dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5a97b-128">Application dialog box</span></span>  
  
     <span data-ttu-id="5a97b-129">È possibile creare una finestra di dialogo dell'applicazione in cui vengono richieste le informazioni di connessione e quindi viene chiamato **SQLDriverConnect** con un handle di finestra null e *DriverCompletion* impostato su SQL_DRIVER_NOPROMPT.</span><span class="sxs-lookup"><span data-stu-id="5a97b-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="5a97b-130">Queste impostazioni impediscono di aprire la finestra di dialogo del driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="5a97b-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="5a97b-131">Questo metodo viene utilizzato quando è importante controllare l'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="5a97b-132">Finestra di dialogo del driver</span><span class="sxs-lookup"><span data-stu-id="5a97b-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="5a97b-133">È possibile codificare l'applicazione per passare un handle di finestra valido a **SQLDriverConnect** e impostare il parametro *DriverCompletion* su SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT o SQL_DRIVER_COMPLETE_REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="5a97b-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="5a97b-134">Il driver genera quindi una finestra di dialogo per richiedere all'utente le informazioni di connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="5a97b-135">Questo metodo semplifica il codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="5a97b-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="5a97b-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="5a97b-137">**SQLBrowseConnect**, ad esempio **SQLDriverConnect**, usa una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="5a97b-138">Tuttavia, usando **SQLBrowseConnect**, un'applicazione può creare una stringa di connessione completa in modo iterativo con l'origine dati in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a97b-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="5a97b-139">In questo modo, l'applicazione può eseguire due operazioni:</span><span class="sxs-lookup"><span data-stu-id="5a97b-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="5a97b-140">Compilare finestre di dialogo proprie per richiedere tali informazioni, mantenendo in tal modo il controllo sull'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="5a97b-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="5a97b-141">Esplorare il sistema per individuare origini dati che possano essere utilizzate da un driver specifico, possibilmente in diversi passaggi.</span><span class="sxs-lookup"><span data-stu-id="5a97b-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="5a97b-142">L'utente, ad esempio, potrebbe esplorare innanzitutto la rete per individuare i server e, dopo averne scelto uno, esplorare il server per individuare i database accessibili dal driver.</span><span class="sxs-lookup"><span data-stu-id="5a97b-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="5a97b-143">Quando **SQLBrowseConnect** completa una connessione, restituisce una stringa di connessione che può essere usata nelle chiamate successive a **SQLDriverConnect**.</span><span class="sxs-lookup"><span data-stu-id="5a97b-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="5a97b-144">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce sempre SQL_SUCCESS_WITH_INFO in un oggetto **SQLConnect**, **SQLDriverConnect**o **SQLBrowseConnect**riuscito.</span><span class="sxs-lookup"><span data-stu-id="5a97b-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="5a97b-145">Quando un'applicazione ODBC chiama **SQLGetDiagRec** dopo avere SQL_SUCCESS_WITH_INFO, può ricevere i messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a97b-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="5a97b-146">5701</span><span class="sxs-lookup"><span data-stu-id="5a97b-146">5701</span></span>  
 <span data-ttu-id="5a97b-147">Indica che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha inserito il contesto dell'utente nel database predefinito specificato nell'origine dati o nel database predefinito specificato per l'ID di accesso utilizzato nella connessione se l'origine dati non dispone di un database predefinito.</span><span class="sxs-lookup"><span data-stu-id="5a97b-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="5a97b-148">5703</span><span class="sxs-lookup"><span data-stu-id="5a97b-148">5703</span></span>  
 <span data-ttu-id="5a97b-149">Indica la lingua utilizzata nel server.</span><span class="sxs-lookup"><span data-stu-id="5a97b-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="5a97b-150">Nell'esempio seguente viene riportato il messaggio restituito in una connessione eseguita correttamente dall'amministratore di sistema:</span><span class="sxs-lookup"><span data-stu-id="5a97b-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="5a97b-151">È possibile ignorare i messaggi 5701 e 5703, in quanto di natura esclusivamente informativa.</span><span class="sxs-lookup"><span data-stu-id="5a97b-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="5a97b-152">Non è consigliabile, tuttavia, ignorare un codice restituito di SQL_SUCCESS_WITH_INFO, in quanto è possibile che vengano generati messaggi diversi da 5701 o 5703.</span><span class="sxs-lookup"><span data-stu-id="5a97b-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="5a97b-153">Se, ad esempio, un driver si connette a un server che esegue un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con le stored procedure di catalogo obsolete, uno degli errori restituiti tramite **SQLGetDiagRec** dopo un SQL_SUCCESS_WITH_INFO è il seguente:</span><span class="sxs-lookup"><span data-stu-id="5a97b-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="5a97b-154">La funzione di gestione degli errori di un'applicazione per le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connessioni deve chiamare **SQLGetDiagRec** fino a quando non restituisce SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="5a97b-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="5a97b-155">Deve quindi agire su tutti i messaggi diversi da quelli con codice *pfNative* 5701 o 5703.</span><span class="sxs-lookup"><span data-stu-id="5a97b-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a97b-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a97b-156">See Also</span></span>  
 [<span data-ttu-id="5a97b-157">Comunicazione con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="5a97b-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
