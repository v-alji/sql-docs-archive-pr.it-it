---
title: Accesso alle informazioni di diagnostica nel log degli eventi estesi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714292"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="9b1ce-102">Accesso alle informazioni di diagnostica nel registro eventi estesi</span><span class="sxs-lookup"><span data-stu-id="9b1ce-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="9b1ce-103">A partire da [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client e la traccia di accesso ai dati ([traccia di accesso ai dati](https://go.microsoft.com/fwlink/?LinkId=125805)) sono stati aggiornati per semplificare l'ottenimento di informazioni di diagnostica sugli errori di connessione dal buffer circolare della connettività e dalle informazioni sulle prestazioni dell'applicazione dal registro eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="9b1ce-104">Per ulteriori informazioni sulla lettura del log degli eventi estesi, vedere [View Event Session Data](../../../database-engine/view-event-session-data.md) (Visualizzare i dati di una sessione di eventi).</span><span class="sxs-lookup"><span data-stu-id="9b1ce-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b1ce-105">Questa funzionalità è destinata esclusivamente alla risoluzione dei problemi e a fini diagnostici e potrebbe non essere appropriata per il controllo o per scopi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b1ce-106">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9b1ce-106">Remarks</span></span>  
 <span data-ttu-id="9b1ce-107">Per le operazioni di connessione, tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client verrà inviato un ID di connessione client.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="9b1ce-108">Se la connessione non riesce, è possibile accedere al buffer circolare della connettività ([risoluzione dei problemi di connettività in SQL Server 2008 con il buffer circolare della connettività](https://go.microsoft.com/fwlink/?LinkId=207752)) e individuare il `ClientConnectionID` campo e ottenere informazioni di diagnostica sull'errore di connessione.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="9b1ce-109">Gli ID di connessione client vengono registrati nel buffer circolare solo se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="9b1ce-110">In caso di errore di connessione prima dell'invio del pacchetto di preaccesso, l'ID di connessione client non verrà generato. L'ID di connessione client è un GUID a 16 byte.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="9b1ce-111">È possibile trovare l'ID di connessione client anche nella destinazione di output degli eventi estesi, se l'azione `client_connection_id` viene aggiunta agli eventi in una sessione di eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="9b1ce-112">È possibile abilitare la traccia di accesso ai dati, eseguire di nuovo il comando di connessione e osservare il campo `ClientConnectionID` nella traccia di accesso ai dati per un'operazione con errori, se è necessaria ulteriore assistenza diagnostica.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="9b1ce-113">Se si utilizza ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client e una connessione ha esito positivo, è possibile ottenere l'ID connessione client utilizzando l' `SQL_COPT_SS_CLIENT_CONNECTION_ID` attributo con [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="9b1ce-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 <span data-ttu-id="9b1ce-114">Tramite [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client viene inviato anche un ID attività specifico del thread.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-114">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="9b1ce-115">L'ID attività viene acquisito nelle sessioni di eventi estesi se avviate con l'opzione TRACK_CAUSAILITY abilitata.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="9b1ce-116">Per problemi di prestazioni con una connessione attiva, è possibile ottenere l'ID attività dalla traccia di accesso ai dati del client (campo`ActivityID`) e individuare quindi l'ID attività nell'output degli eventi estesi.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="9b1ce-117">L'ID attività negli eventi estesi è un GUID a 16 byte (diverso dal GUID per l'ID di connessione client) accodato con un numero di sequenza a quattro byte.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="9b1ce-118">Il numero di sequenza rappresenta l'ordine di una richiesta all'interno di un thread e indica l'ordine relativo di istruzioni batch e RPC per il thread.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="9b1ce-119">L'`ActivityID` viene inviato facoltativamente per istruzioni batch SQL e richieste RPC quando la traccia di accesso ai dati è abilitata e il diciottesimo bit nella configurazione della traccia di accesso ai dati è abilitato.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="9b1ce-120">Di seguito è riportato un esempio di utilizzo di [!INCLUDE[tsql](../../../includes/tsql-md.md)] per avviare una sessione di eventi estesi che verrà archiviata in un buffer circolare e verrà registrato l'ID attività inviato da un client in operazioni RPC e batch.</span><span class="sxs-lookup"><span data-stu-id="9b1ce-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="9b1ce-121">File di controllo</span><span class="sxs-lookup"><span data-stu-id="9b1ce-121">Control File</span></span>  
 <span data-ttu-id="9b1ce-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], il contenuto del file di controllo di SQL Server Native Client (ctrl.guid.snac11) è:</span><span class="sxs-lookup"><span data-stu-id="9b1ce-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="9b1ce-123">File MOF</span><span class="sxs-lookup"><span data-stu-id="9b1ce-123">MOF File</span></span>  
 <span data-ttu-id="9b1ce-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], il contenuto del file MOF di SQL Server Native Client è:</span><span class="sxs-lookup"><span data-stu-id="9b1ce-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b1ce-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b1ce-125">See Also</span></span>  
 [<span data-ttu-id="9b1ce-126">Gestione di errori e messaggi</span><span class="sxs-lookup"><span data-stu-id="9b1ce-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
