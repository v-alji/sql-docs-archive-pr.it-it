---
title: MSSQLSERVER_8992 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8992 (Database Engine error)
ms.assetid: 68467e6a-09d8-478f-8bd9-3bb09453ada3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: adcf914accab43202cf148fe852b334c9b078287
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638406"
---
# <a name="mssqlserver_8992"></a><span data-ttu-id="df9cc-102">MSSQLSERVER_8992</span><span class="sxs-lookup"><span data-stu-id="df9cc-102">MSSQLSERVER_8992</span></span>
    
## <a name="details"></a><span data-ttu-id="df9cc-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="df9cc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df9cc-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="df9cc-104">Product Name</span></span>|<span data-ttu-id="df9cc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="df9cc-105">SQL Server</span></span>|  
|<span data-ttu-id="df9cc-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="df9cc-106">Event ID</span></span>|<span data-ttu-id="df9cc-107">8992</span><span class="sxs-lookup"><span data-stu-id="df9cc-107">8992</span></span>|  
|<span data-ttu-id="df9cc-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="df9cc-108">Event Source</span></span>|<span data-ttu-id="df9cc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="df9cc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="df9cc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="df9cc-110">Component</span></span>|<span data-ttu-id="df9cc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="df9cc-111">SQLEngine</span></span>|  
|<span data-ttu-id="df9cc-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="df9cc-112">Symbolic Name</span></span>|<span data-ttu-id="df9cc-113">DBCC3_CHECK_CATALOG</span><span class="sxs-lookup"><span data-stu-id="df9cc-113">DBCC3_CHECK_CATALOG</span></span>|  
|<span data-ttu-id="df9cc-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="df9cc-114">Message Text</span></span>|<span data-ttu-id="df9cc-115">Messaggio di controllo del catalogo ERROR Level LEVEL State STATE: MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="df9cc-115">Check Catalog Msg ERROR Level LEVEL State STATE: MESSAGE.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df9cc-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="df9cc-116">Explanation</span></span>  
 <span data-ttu-id="df9cc-117">DBCC CHECKCATALOG o DBCC CHECKDB ha rilevato un'incoerenza nelle tabelle di metadati di sistema per l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="df9cc-117">DBCC CHECKCATALOG or DBCC CHECKDB found an inconsistency in the system metadata tables for the specified object.</span></span> <span data-ttu-id="df9cc-118">Ciò significa che vi è un'incoerenza tra l'ID dell'oggetto registrato e l'oggetto specificato nel messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="df9cc-118">That is, there is an inconsistency between the recorded object ID and the object specified in error message.</span></span>  
  
 <span data-ttu-id="df9cc-119">Questo errore può verificarsi quando una o più tabelle di sistema sono state aggiornate manualmente in modo da creare un'incoerenza nei metadati di sistema.</span><span class="sxs-lookup"><span data-stu-id="df9cc-119">This error can occur when one or more system tables has been manually updated in a way that creates an inconsistency in the system metadata.</span></span> <span data-ttu-id="df9cc-120">Un utente, ad esempio, può avere manualmente eliminato un oggetto dalla tabella **sysobjects** senza rimuovere le righe associate in altre tabelle, quali **sysindexes** e **syscolumns**.</span><span class="sxs-lookup"><span data-stu-id="df9cc-120">For example, a user may have manually deleted an object from the **sysobjects** table without removing associated rows in other tables such as **sysindexes** and **syscolumns**.</span></span>  
  
 <span data-ttu-id="df9cc-121">Questo errore può verificarsi quando si esegue DBCC CHECKDB su un database aggiornato da SQL Server 2000 a SQL Server 2005 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="df9cc-121">This error can occur when running DBCC CHECKDB against a database that has been upgraded from SQL Server 2000 to SQL Server 2005 or later.</span></span> <span data-ttu-id="df9cc-122">Poiché in SQL Server 2000 DBCC CHECKDB non include la funzionalità DBCC CHECKCATALOG, l'errore non viene rilevato prima dell'aggiornamento a meno di non eseguire DBCC CHECKCATALOG in modo specifico sul database.</span><span class="sxs-lookup"><span data-stu-id="df9cc-122">In SQL Server 2000, DBCC CHECKDB did not include DBCC CHECKCATALOG functionality, so the error would not be caught before upgrade unless DBCC CHECKCATALOG was specifically executed against the database in SQL Server 2000.</span></span>  
  
 <span data-ttu-id="df9cc-123">È possibile che venga visualizzato uno degli errori seguenti insieme all'errore 8992:</span><span class="sxs-lookup"><span data-stu-id="df9cc-123">You may see any of the following errors in conjunction with error 8992:</span></span>  
  
 <span data-ttu-id="df9cc-124">Messaggio 3851 - Trovata una riga non valida (%ls) nella tabella di sistema sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-124">Msg 3851 - An invalid row (%ls) was found in the system table sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-125">Messaggio 3852 - Per la riga (%ls) di sys.%ls%ls non esiste una riga corrispondente (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-125">Msg 3852 - Row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-126">Messaggio 3853 - Per l'attributo (%ls) della riga (%ls) di sys.%ls%ls non esiste una riga corrispondente (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-126">3853 - Attribute (%ls) of row (%ls) in sys.%ls%ls does not have a matching row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-127">Messaggio 3854 - Per l'attributo (%ls) della riga (%ls) di sys.%ls%ls esiste una riga corrispondente (%ls) in sys.%ls%ls che non è valida.</span><span class="sxs-lookup"><span data-stu-id="df9cc-127">3854 - Attribute (%ls) of row (%ls) in sys.%ls%ls has a matching row (%ls) in sys.%ls%ls that is invalid.</span></span>  
  
 <span data-ttu-id="df9cc-128">Messaggio 3855 - L'attributo (%ls) esiste senza una riga (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-128">3855 - Attribute (%ls) exists without a row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-129">Messaggio 3856 - L'attributo (%ls) esiste, ma non dovrebbe esistere per la riga (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-129">3856 - Attribute (%ls) exists but should not for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-130">Messaggio 3857 - L'attributo (%ls) è necessario ma è assente per la riga (%ls) in sys.%ls%ls.</span><span class="sxs-lookup"><span data-stu-id="df9cc-130">3857 - The attribute (%ls) is required but is missing for row (%ls) in sys.%ls%ls.</span></span>  
  
 <span data-ttu-id="df9cc-131">Messaggio 3858 - Il valore dell'attributo (%ls) della riga (%ls) in sys.%ls%ls non è valido.</span><span class="sxs-lookup"><span data-stu-id="df9cc-131">3858 - The attribute (%ls) of row (%ls) in sys.%ls%ls has an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df9cc-132">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="df9cc-132">User Action</span></span>  
  
### <a name="drop-and-re-create-the-specified-object"></a><span data-ttu-id="df9cc-133">Rimuovere e ricreare l'oggetto specificato</span><span class="sxs-lookup"><span data-stu-id="df9cc-133">Drop and Re-create the Specified Object</span></span>  
 <span data-ttu-id="df9cc-134">Se possibile, rimuovere e ricreare l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="df9cc-134">If possible, drop and recreate the specified object.</span></span> <span data-ttu-id="df9cc-135">Se, ad esempio, l'oggetto è una stored procedure di tipo definito dall'utente (UDT), una nuova creazione dell'oggetto potrebbe risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="df9cc-135">For example, if the object is a stored procedure or user-defined type, recreating the object may resolve the problem.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="df9cc-136">Eseguire un ripristino da backup</span><span class="sxs-lookup"><span data-stu-id="df9cc-136">Restore from Backup</span></span>  
 <span data-ttu-id="df9cc-137">Se il problema non è correlato all'hardware ed è disponibile un backup valido noto, ripristinare il database dal backup.</span><span class="sxs-lookup"><span data-stu-id="df9cc-137">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span> <span data-ttu-id="df9cc-138">Questa azione è utile solo se il backup non contiene errori dei metadati.</span><span class="sxs-lookup"><span data-stu-id="df9cc-138">This action is only applicable if the backup does not contain the metadata error.</span></span>  
  
### <a name="export-the-data-to-a-new-database"></a><span data-ttu-id="df9cc-139">Esportare i dati in un nuovo database</span><span class="sxs-lookup"><span data-stu-id="df9cc-139">Export the Data to a New Database</span></span>  
 <span data-ttu-id="df9cc-140">Se nel backup sono contenuti anche metadati incoerenti, è necessario creare un nuovo database in cui esportare il contenuto di quello esistente.</span><span class="sxs-lookup"><span data-stu-id="df9cc-140">If the backup also contains the metadata inconsistency, you need to create a new database and export the contents of the existing database to the new database.</span></span>  
  
### <a name="dbcc-checkdb-cannot-repair-this-error"></a><span data-ttu-id="df9cc-141">Impossibile correggere questo errore con DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="df9cc-141">DBCC CHECKDB Cannot Repair This Error</span></span>  
 <span data-ttu-id="df9cc-142">Impossibile correggere questo errore.</span><span class="sxs-lookup"><span data-stu-id="df9cc-142">This error cannot be repaired.</span></span>  <span data-ttu-id="df9cc-143">Se non è possibile ripristinare il database da un backup, contattare il Servizio Supporto Tecnico Clienti [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df9cc-143">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
### <a name="do-not-manually-update-system-tables"></a><span data-ttu-id="df9cc-144">Non aggiornare manualmente le tabelle di sistema</span><span class="sxs-lookup"><span data-stu-id="df9cc-144">Do Not Manually Update System Tables</span></span>  
 <span data-ttu-id="df9cc-145">Non effettuare aggiornamenti manuali alle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="df9cc-145">Do not make manual updates to system tables.</span></span> <span data-ttu-id="df9cc-146">SQL Server non supporta alcuna modifica manuale ai database di sistema.</span><span class="sxs-lookup"><span data-stu-id="df9cc-146">SQL Server does not support any manual changes to system databases.</span></span> <span data-ttu-id="df9cc-147">Se si aggiorna una tabella di sistema in un database di SQL Server, vengono registrati due eventi, evento ID 17659 ed evento ID 3859.</span><span class="sxs-lookup"><span data-stu-id="df9cc-147">If you update a system table in a SQL Server database, two events (event ID 17659 and event ID 3859) are logged.</span></span> <span data-ttu-id="df9cc-148">Per ulteriori informazioni, vedere l'articolo della Knowledge Base 2688307 relativo agli eventi ID 17659 e ID 3859 registrati durante l'aggiornamento di tabelle di sistema in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df9cc-148">For more information, see KB article 2688307, "Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9cc-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="df9cc-149">See Also</span></span>  
 [<span data-ttu-id="df9cc-150">Gli eventi con ID 17659 e ID 3859 vengono registrati durante l'aggiornamento delle tabelle di sistema in un database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="df9cc-150">Event ID 17659 and event ID 3859 are logged when you update system tables in a SQL Server database</span></span>](https://support.microsoft.com/kb/2688307/EN-US)  
  
  
