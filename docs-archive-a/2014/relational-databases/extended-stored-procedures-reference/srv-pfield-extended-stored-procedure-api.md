---
title: srv_pfield (API Stored procedure estesa) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725800"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="314ff-102">srv_pfield (API della stored procedure estesa)</span><span class="sxs-lookup"><span data-stu-id="314ff-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="314ff-103">Usare in alternativa l'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="314ff-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="314ff-104">Restituisce informazioni su una connessione a un database.</span><span class="sxs-lookup"><span data-stu-id="314ff-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314ff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="314ff-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="314ff-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="314ff-106">Arguments</span></span>  
 <span data-ttu-id="314ff-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="314ff-107">*srvproc*</span></span>  
 <span data-ttu-id="314ff-108">Puntatore che identifica una connessione al database.</span><span class="sxs-lookup"><span data-stu-id="314ff-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="314ff-109">*campo*</span><span class="sxs-lookup"><span data-stu-id="314ff-109">*field*</span></span>  
 <span data-ttu-id="314ff-110">Specifica i dati nella connessione da restituire.</span><span class="sxs-lookup"><span data-stu-id="314ff-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="314ff-111">Valore</span><span class="sxs-lookup"><span data-stu-id="314ff-111">Value</span></span>|<span data-ttu-id="314ff-112">Restituisce</span><span class="sxs-lookup"><span data-stu-id="314ff-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="314ff-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="314ff-113">SRV_APPLNAME</span></span>|<span data-ttu-id="314ff-114">Nome dell'applicazione fornito dal client quando ha stabilito la connessione.</span><span class="sxs-lookup"><span data-stu-id="314ff-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="314ff-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="314ff-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="314ff-116">Flag impostato su TRUE se il client si prepara per un'operazione di copia bulk; in caso contrario, è impostato su FALSE.</span><span class="sxs-lookup"><span data-stu-id="314ff-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="314ff-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="314ff-117">SRV_CLIB</span></span>|<span data-ttu-id="314ff-118">Nome della libreria che consente al client di comunicare con un server.</span><span class="sxs-lookup"><span data-stu-id="314ff-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="314ff-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="314ff-119">SRV_CPID</span></span>|<span data-ttu-id="314ff-120">ID del processo client nel computer di origine client.</span><span class="sxs-lookup"><span data-stu-id="314ff-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="314ff-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="314ff-121">SRV_HOST</span></span>|<span data-ttu-id="314ff-122">Nome del computer del client fornito dal client quando ha stabilito la connessione.</span><span class="sxs-lookup"><span data-stu-id="314ff-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="314ff-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="314ff-123">SRV_LIBVERS</span></span>|<span data-ttu-id="314ff-124">Versione della libreria client.</span><span class="sxs-lookup"><span data-stu-id="314ff-124">The version of the client library.</span></span>|  
|<span data-ttu-id="314ff-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="314ff-125">SRV_LSECURE</span></span>|<span data-ttu-id="314ff-126">Flag.</span><span class="sxs-lookup"><span data-stu-id="314ff-126">A flag.</span></span> <span data-ttu-id="314ff-127">TRUE se la connessione utilizza sicurezza integrata per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="314ff-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="314ff-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="314ff-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="314ff-129">Nome della DLL di rete utilizzata dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="314ff-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="314ff-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="314ff-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="314ff-131">Versione della DLL di rete utilizzata dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="314ff-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="314ff-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="314ff-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="314ff-133">Stringa di connessione passata alla DLL di rete usata per la connessione *srvproc* corrente.</span><span class="sxs-lookup"><span data-stu-id="314ff-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="314ff-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="314ff-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="314ff-135">Stringa che contiene l'handle di pipe di un client connesso oppure valore NULL se il client è connesso in una rete che non utilizza named pipe.</span><span class="sxs-lookup"><span data-stu-id="314ff-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="314ff-136">Per utilizzare questo handle come handle di pipe valido con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convertire questa stringa in numero intero.</span><span class="sxs-lookup"><span data-stu-id="314ff-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="314ff-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="314ff-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="314ff-138">Server dal quale ha eseguito l'accesso il processo del client.</span><span class="sxs-lookup"><span data-stu-id="314ff-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="314ff-139">Se l'accesso è da un client, questo valore è una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="314ff-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="314ff-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="314ff-140">SRV_ROWSENT</span></span>|<span data-ttu-id="314ff-141">Numero di righe già inviate da *srvproc* per il set di risultati corrente.</span><span class="sxs-lookup"><span data-stu-id="314ff-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="314ff-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="314ff-142">SRV_SPID</span></span>|<span data-ttu-id="314ff-143">ID del thread di server di *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="314ff-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="314ff-144">Per le stored procedure estese, questo valore coincide con quello della colonna **kpid** di **sys.sysprocesses** e può cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="314ff-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="314ff-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="314ff-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="314ff-146">Tabella codici utilizzata dal server per interpretare dati multibyte.</span><span class="sxs-lookup"><span data-stu-id="314ff-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="314ff-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="314ff-147">SRV_STATUS</span></span>|<span data-ttu-id="314ff-148">Stato corrente di *srvproc*: in esecuzione o chiusa</span><span class="sxs-lookup"><span data-stu-id="314ff-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="314ff-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="314ff-149">SRV_TYPE</span></span>|<span data-ttu-id="314ff-150">Tipo di connessione di *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="314ff-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="314ff-151">Se viene restituito server, la connessione *srvproc* viene eseguita da un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="314ff-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="314ff-152">Se viene restituito client, la connessione *srvproc* viene eseguita da DB-Library o da un client ODBC.</span><span class="sxs-lookup"><span data-stu-id="314ff-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="314ff-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="314ff-153">SRV_USER</span></span>|<span data-ttu-id="314ff-154">Nome utente della connessione.</span><span class="sxs-lookup"><span data-stu-id="314ff-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="314ff-155">*Len*</span><span class="sxs-lookup"><span data-stu-id="314ff-155">*len*</span></span>  
 <span data-ttu-id="314ff-156">Puntatore a una variabile **int** che contiene la lunghezza del valore *field* restituito.</span><span class="sxs-lookup"><span data-stu-id="314ff-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="314ff-157">Se *len* è NULL, la lunghezza della stringa non viene restituita.</span><span class="sxs-lookup"><span data-stu-id="314ff-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="314ff-158">Restituisce</span><span class="sxs-lookup"><span data-stu-id="314ff-158">Returns</span></span>  
 <span data-ttu-id="314ff-159">Un puntatore a una stringa con terminazione Null che contiene il valore corrente per il campo specificato nella struttura SRV_PROC.</span><span class="sxs-lookup"><span data-stu-id="314ff-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="314ff-160">Se il campo è vuoto, viene restituito un puntatore valido a una stringa vuota e *len* contiene 0.</span><span class="sxs-lookup"><span data-stu-id="314ff-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="314ff-161">Se il campo non è noto, viene restituito NULL e *len* contiene il valore -1.</span><span class="sxs-lookup"><span data-stu-id="314ff-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="314ff-162">È necessario esaminare con attenzione il codice sorgente delle stored procedure estese e testare le DLL compilate prima di installarle in un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="314ff-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="314ff-163">Per informazioni sui test e l'analisi della sicurezza, visitare il sito Web [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="314ff-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
