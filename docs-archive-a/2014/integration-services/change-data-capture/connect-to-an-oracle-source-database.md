---
title: Connettersi a un database di origine Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraDb
ms.assetid: 220cf555-0db2-443c-8f87-8e413f3ca731
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fccba3d11adc67b3f5ef4f8648ec5d0de07a5648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720316"
---
# <a name="connect-to-an-oracle-source-database"></a><span data-ttu-id="3ccfe-102">Connettersi a un database di origine Oracle</span><span class="sxs-lookup"><span data-stu-id="3ccfe-102">Connect to an Oracle Source Database</span></span>
  <span data-ttu-id="3ccfe-103">Utilizzare la pagina Oracle Source per fornire le informazioni necessarie per la connessione al database di origine Oracle.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-103">Use the Oracle Source page to provide the information necessary to connect to the Oracle source database.</span></span> <span data-ttu-id="3ccfe-104">Tramite l'istanza di CDC verranno letti i log di rollforward del database Oracle a cui si è effettuata la connessione.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-104">The CDC instance will read the redo logs of the Oracle database you are connected to.</span></span>  
  
 <span data-ttu-id="3ccfe-105">**Oracle Connect String**</span><span class="sxs-lookup"><span data-stu-id="3ccfe-105">**Oracle Connect String**</span></span>  
 <span data-ttu-id="3ccfe-106">Immettere la stringa di connessione Oracle nel computer contenente il database Oracle in uso.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-106">Enter the Oracle connect string to the computer with the Oracle database you are using.</span></span> <span data-ttu-id="3ccfe-107">La stringa di connessione viene scritta in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ccfe-107">The connect string is written in one of the following ways:</span></span>  
  
 `host[:port][/service name]`  
  
 <span data-ttu-id="3ccfe-108">Nella stringa di connessione è anche possibile specificare un descrittore della connessione di rete Oracle, ad esempio `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span><span class="sxs-lookup"><span data-stu-id="3ccfe-108">The connection string can also specify an Oracle Net connect descriptor, for example, `(DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=erp.contoso.com) (PORT=1521)) (CONNECT_DATA=(SERVICE_NAME=orcl)))`</span></span>  
  
 <span data-ttu-id="3ccfe-109">Se si utilizza un server di elenchi in linea o nomi TNS, la stringa di connessione può essere il nome della connessione.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-109">If using a directory server or tnsnames, the connect string can be the name of the connection.</span></span>  
  
 <span data-ttu-id="3ccfe-110">**Oracle Log Mining Authentication**</span><span class="sxs-lookup"><span data-stu-id="3ccfe-110">**Oracle Log Mining Authentication**</span></span>  
 <span data-ttu-id="3ccfe-111">Per immettere le credenziali per l'utente del database Oracle autorizzato per il log mining, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ccfe-111">To enter the credentials for the Oracle database user that is authorized for log mining, select one of the following:</span></span>  
  
-   <span data-ttu-id="3ccfe-112">**Windows Authentication**: selezionare questa opzione per utilizzare le credenziali del dominio Windows correnti.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-112">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="3ccfe-113">È possibile utilizzare questa opzione solo se il database Oracle è configurato per l'utilizzo dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-113">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="3ccfe-114">**Oracle Authentication**: se si seleziona questa opzione, è necessario digitare il **nome utente** e la **password** dell'utente nel database Oracle a cui si effettua la connessione.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-114">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Oracle database you are connecting to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ccfe-115">Per poter essere un utente del log mining un utente deve disporre dei privilegi seguenti per il database Oracle.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-115">A user must have the following privileges granted in the Oracle database to be a log-mining user.</span></span>  
> 
>  -   <span data-ttu-id="3ccfe-116">SELECT per \<any-captured-table></span><span class="sxs-lookup"><span data-stu-id="3ccfe-116">SELECT on \<any-captured-table></span></span>  
> -   <span data-ttu-id="3ccfe-117">SELECT ANY TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="3ccfe-117">SELECT ANY TRANSACTION</span></span>  
> -   <span data-ttu-id="3ccfe-118">EXECUTE on DBMS LOGMNR</span><span class="sxs-lookup"><span data-stu-id="3ccfe-118">EXECUTE on DBMS LOGMNR</span></span>  
> -   <span data-ttu-id="3ccfe-119">SELECT on V$LOGMNR CONTENTS</span><span class="sxs-lookup"><span data-stu-id="3ccfe-119">SELECT on V$LOGMNR CONTENTS</span></span>  
> -   <span data-ttu-id="3ccfe-120">SELECT on V$ARCHIVED LOG</span><span class="sxs-lookup"><span data-stu-id="3ccfe-120">SELECT on V$ARCHIVED LOG</span></span>  
> -   <span data-ttu-id="3ccfe-121">SELECT on V$LOG</span><span class="sxs-lookup"><span data-stu-id="3ccfe-121">SELECT on V$LOG</span></span>  
> -   <span data-ttu-id="3ccfe-122">SELECT on V$LOGFILE</span><span class="sxs-lookup"><span data-stu-id="3ccfe-122">SELECT on V$LOGFILE</span></span>  
> -   <span data-ttu-id="3ccfe-123">SELECT on V$DATABASE</span><span class="sxs-lookup"><span data-stu-id="3ccfe-123">SELECT on V$DATABASE</span></span>  
> -   <span data-ttu-id="3ccfe-124">SELECT on V$THREAD</span><span class="sxs-lookup"><span data-stu-id="3ccfe-124">SELECT on V$THREAD</span></span>  
> -   <span data-ttu-id="3ccfe-125">SELECT on ALL INDEXES</span><span class="sxs-lookup"><span data-stu-id="3ccfe-125">SELECT on ALL INDEXES</span></span>  
> -   <span data-ttu-id="3ccfe-126">SELECT on ALL OBJECTS</span><span class="sxs-lookup"><span data-stu-id="3ccfe-126">SELECT on ALL OBJECTS</span></span>  
> -   <span data-ttu-id="3ccfe-127">SELECT on DBA OBJECTS</span><span class="sxs-lookup"><span data-stu-id="3ccfe-127">SELECT on DBA OBJECTS</span></span>  
> -   <span data-ttu-id="3ccfe-128">SELECT on ALL TABLES</span><span class="sxs-lookup"><span data-stu-id="3ccfe-128">SELECT on ALL TABLES</span></span>  
> 
>  <span data-ttu-id="3ccfe-129">Se non è possibile concedere alcuni di questi privilegi a un V$xxx, concederli a V_S$xxx.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-129">If any of these privileges cannot be granted to a V$xxx, then grant them to the V_S$xxx.</span></span>  
  
 <span data-ttu-id="3ccfe-130">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="3ccfe-130">**Test Connection**</span></span>  
 <span data-ttu-id="3ccfe-131">Fare clic su **Test connessione** per determinare se è stata stabilita una connessione al computer remoto in cui è presente il database Oracle.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-131">Click **Test Connection** to determine whether you established a connection with the remote computer that has the Oracle database.</span></span> <span data-ttu-id="3ccfe-132">Una finestra di dialogo informerà l'utente se la connessione è stata stabilita correttamente.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-132">A dialog box opens to inform you whether the connection was successful.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3ccfe-133">A causa di un problema noto, la connessione al database di origine Oracle potrebbe non riuscire se la progettazione di CDC non viene eseguita con i privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3ccfe-133">Due to a known issue connection to the Oracle source database may fail if the CDC Designer is not run as an administrator.</span></span> <span data-ttu-id="3ccfe-134">Se la connessione non può essere stabilita, chiudere e riavviare la finestra di progettazione di CDC utilizzando l'opzione **Esegui come amministratore** .</span><span class="sxs-lookup"><span data-stu-id="3ccfe-134">If connection fails, close and restart the CDC Designer using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="3ccfe-135">Dopo avere completato l'immissione delle informazioni in questa pagina, scegliere **Avanti** in [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span><span class="sxs-lookup"><span data-stu-id="3ccfe-135">After you finish entering information on this page, click **Next** to [Select Oracle Tables and Columns](select-oracle-tables-and-columns.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccfe-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ccfe-136">See Also</span></span>  
 <span data-ttu-id="3ccfe-137">[Procedura di creazione dell'istanza del database delle modifiche di SQL Server](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="3ccfe-137">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="3ccfe-138">Modificare le proprietà dell'istanza</span><span class="sxs-lookup"><span data-stu-id="3ccfe-138">Edit Instance Properties</span></span>](edit-instance-properties.md)  
  
  
