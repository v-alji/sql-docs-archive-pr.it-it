---
title: SQLDriverConnect | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721436"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="17042-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="17042-102">SQLDriverConnect</span></span>
  <span data-ttu-id="17042-103">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client definisce attributi di connessione che sostituiscono o migliorano le parole chiave della stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="17042-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="17042-104">Per diverse parole chiave della stringa di connessione sono disponibili valori predefiniti specificati dal driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="17042-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="17042-105">Per un elenco delle parole chiave disponibili nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client, vedere [utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="17042-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="17042-106">Per ulteriori informazioni sugli [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attributi di connessione e sui comportamenti predefiniti del driver, vedere [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="17042-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="17042-107">Per informazioni sulle parole chiave della stringa di connessione valide per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client, vedere [utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="17042-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="17042-108">Se il `SQLDriverConnect` valore del parametro *DriverCompletion* è SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE o SQL_DRIVER_COMPLETE_REQUIRED, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client recupera i valori delle parole chiave dalla finestra di dialogo visualizzata.</span><span class="sxs-lookup"><span data-stu-id="17042-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="17042-109">Se il valore della parola chiave viene passato nella stringa di connessione e l'utente non modifica il valore per la parola chiave nella finestra di dialogo, il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utilizza il valore dalla stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="17042-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="17042-110">Se il valore non è impostato nella stringa di connessione e l'utente non esegue alcuna assegnazione nella finestra di dialogo, il driver utilizza il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="17042-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="17042-111">`SQLDriverConnect`è necessario specificare un *WindowHandle* valido quando un qualsiasi valore *DriverCompletion* richiede o potrebbe richiedere la visualizzazione della finestra di dialogo di connessione del driver.</span><span class="sxs-lookup"><span data-stu-id="17042-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="17042-112">Un handle non valido restituisce SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="17042-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="17042-113">Specificare la parola chiave DRIVER o DSN.</span><span class="sxs-lookup"><span data-stu-id="17042-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="17042-114">ODBC dichiara che un driver utilizza la parola chiave più a sinistra tra le due e ignora l'altra se sono specificate entrambe.</span><span class="sxs-lookup"><span data-stu-id="17042-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="17042-115">Se viene specificato il DRIVER oppure è l'oggetto più a sinistra dei due e il `SQLDriverConnect` valore del parametro *DriverCompletion* è SQL_DRIVER_NOPROMPT, la parola chiave server e un valore appropriato sono obbligatori.</span><span class="sxs-lookup"><span data-stu-id="17042-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="17042-116">Quando si specifica SQL_DRIVER_NOPROMPT, le parole chiave di autenticazione utente devono essere presenti con valori.</span><span class="sxs-lookup"><span data-stu-id="17042-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="17042-117">Il driver garantisce la presenza della stringa "Trusted_Connection=yes" o delle parole chiave UID e PWD.</span><span class="sxs-lookup"><span data-stu-id="17042-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="17042-118">Se il valore del parametro *DriverCompletion* è SQL_DRIVER_NOPROMPT o SQL_DRIVER_COMPLETE_REQUIRED e la lingua o il database deriva dalla stringa di connessione e non è valido, `SQLDriverConnect` restituisce SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="17042-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="17042-119">Se il valore del parametro *DriverCompletion* è SQL_DRIVER_NOPROMPT o SQL_DRIVER_COMPLETE_REQUIRED e la lingua o il database deriva dalle definizioni delle origini dati ODBC e non è valido, `SQLDriverConnect` utilizza la lingua o il database predefinito per l'ID utente specificato e restituisce SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="17042-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="17042-120">Se il valore del parametro *DriverCompletion* è SQL_DRIVER_COMPLETE o SQL_DRIVER_PROMPT e se la lingua o il database non è valido, `SQLDriverConnect` Visualizza nuovamente la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="17042-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="17042-121">Supporto di SQLDriverConnect per il ripristino di emergenza a disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="17042-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="17042-122">Per ulteriori informazioni sull'utilizzo `SQLDriverConnect` di per la connessione a un [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, vedere [SQL Server Native client supporto per la disponibilità elevata e il ripristino di emergenza](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="17042-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="17042-123">Supporto di SQLDriverConnect per nomi SPN (Service Principal Name)</span><span class="sxs-lookup"><span data-stu-id="17042-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="17042-124">SQLDDriverConnect utilizzerà la finestra di dialogo di accesso ODBC boxwhen la richiesta di conferma è abilitata.</span><span class="sxs-lookup"><span data-stu-id="17042-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="17042-125">Ciò consente di immettere i nomi SPN per il server principale e per il relativo partner di failover.</span><span class="sxs-lookup"><span data-stu-id="17042-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="17042-126">SQLDriverConnect accetterà le nuove parole chiave della stringa `ServerSPN` di connessione e `FailoverPartnerSPN` rileverà i nuovi attributi di connessione SQL_COPT_SS_SERVER_SPN e SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="17042-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="17042-127">Quando un attributo di connessione viene specificato più di una volta, un valore impostato a livello di programmazione ha la precedenza sul valore in un DSN e su un valore in una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="17042-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="17042-128">Un valore in un DSN ha la precedenza su un valore in una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="17042-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="17042-129">Quando si apre una connessione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client imposta SQL_COPT_SS_MUTUALLY_AUTHENTICATED e SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD sul metodo di autenticazione utilizzato per aprire la connessione.</span><span class="sxs-lookup"><span data-stu-id="17042-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="17042-130">Per ulteriori informazioni sui nomi SPN, vedere [nomi dell'entità servizio &#40;spn&#41; nelle connessioni Client &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="17042-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="17042-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="17042-131">Examples</span></span>  
 <span data-ttu-id="17042-132">Nella chiamata seguente viene illustrata la quantità minima di dati necessaria per `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="17042-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="17042-133">Le stringhe di connessione seguenti illustrano i dati minimi necessari quando il valore del parametro *DriverCompletion* è SQL_DRIVER_NOPROMPT:</span><span class="sxs-lookup"><span data-stu-id="17042-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="17042-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17042-134">See Also</span></span>  
 <span data-ttu-id="17042-135">[SQLDriverConnect (funzione)](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="17042-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="17042-136">[Dettagli di implementazione dell'API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="17042-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="17042-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17042-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="17042-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17042-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="17042-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17042-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
