---
title: Confronto di tabelle replicate al fine di individuare le differenze (programmazione della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- tablediff utility
- comparing replicated tables
ms.assetid: cd253a17-0c85-42b4-912c-690169ebe799
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0d804c7d4ac9cc54fa144b7054c6032663b76c0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725583"
---
# <a name="compare-replicated-tables-for-differences-replication-programming"></a><span data-ttu-id="42f08-102">Confronto di tabelle replicate al fine di individuare le differenze (programmazione della replica)</span><span class="sxs-lookup"><span data-stu-id="42f08-102">Compare Replicated Tables for Differences (Replication Programming)</span></span>
  <span data-ttu-id="42f08-103">La convalida degli articoli consente di determinare se i dati pubblicati per gli articoli di tabella nel server di pubblicazione e nel Sottoscrittore non sono identici, fattore che può indicare la mancanza di convergenza.</span><span class="sxs-lookup"><span data-stu-id="42f08-103">Article validation is used to determine if published data for table articles at the Publisher and Subscriber are not identical, which can indicate non-convergence.</span></span> <span data-ttu-id="42f08-104">Per altre informazioni, vedere [Convalidare i dati replicati](../validate-data-at-the-subscriber.md).</span><span class="sxs-lookup"><span data-stu-id="42f08-104">For more information, see [Validate Replicated Data](../validate-data-at-the-subscriber.md).</span></span> <span data-ttu-id="42f08-105">La convalida restituisce tuttavia solo un risultato positivo o negativo e non fornisce informazioni sulle differenze specifiche tra le tabelle di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-105">However, validation only returns pass or fail information and does not provide any information about what is different between the source and destination tables.</span></span> <span data-ttu-id="42f08-106">L'utilità del prompt dei comandi **tablediff** restituisce informazioni dettagliate sulle differenze tra due tabelle e può anche generare uno script [!INCLUDE[tsql](../../../includes/tsql-md.md)] per ripristinare la convergenza tra una sottoscrizione e i dati nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-106">The **tablediff** command prompt utility returns detailed difference information between two tables and can even generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script to bring a subscription into convergence with data at the Publisher.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42f08-107">L'utilità **tablediff** è supportata solo per i server [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42f08-107">The **tablediff** utility is only supported for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] servers.</span></span>  
  
### <a name="to-compare-replicated-tables-for-differences-using-tablediff"></a><span data-ttu-id="42f08-108">Per confrontare le tabelle replicate al fine di individuare le differenze mediante tablediff</span><span class="sxs-lookup"><span data-stu-id="42f08-108">To compare replicated tables for differences using tablediff</span></span>  
  
1.  <span data-ttu-id="42f08-109">Dal prompt dei comandi in qualsiasi server in una topologia di replica, eseguire l' [tablediff Utility](../../../tools/tablediff-utility.md).</span><span class="sxs-lookup"><span data-stu-id="42f08-109">From the command prompt at any server in a replication topology, run the [tablediff Utility](../../../tools/tablediff-utility.md).</span></span> <span data-ttu-id="42f08-110">Specificare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="42f08-110">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="42f08-111">**-sourceserver** : nome del server i cui dati sono considerati corretti, generalmente il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-111">**-sourceserver** - name of the server on which the data is known to be correct, usually the Publisher.</span></span>  
  
    -   <span data-ttu-id="42f08-112">**-sourcedatabase** : nome del database contenente i dati corretti.</span><span class="sxs-lookup"><span data-stu-id="42f08-112">**-sourcedatabase** - name of the database containing the correct data.</span></span>  
  
    -   <span data-ttu-id="42f08-113">**-sourcetable** : nome della tabella di origine dell'articolo da confrontare.</span><span class="sxs-lookup"><span data-stu-id="42f08-113">**-sourcetable** - name of the source table for the article being compared.</span></span>  
  
    -   <span data-ttu-id="42f08-114">(Facoltativo) **-sourceschema** : proprietario dello schema della tabella di origine, se diverso dallo schema predefinito.</span><span class="sxs-lookup"><span data-stu-id="42f08-114">(Optional) **-sourceschema** - schema owner of the source table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="42f08-115">(Facoltativo) **-sourceuser** e **-sourcepassword** quando si utilizza l'autenticazione di SQL Server per la connessione al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-115">(Optional) **-sourceuser** and **-sourcepassword** when using SQL Server Authentication to connect to the Publisher.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="42f08-116">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="42f08-116">When possible, use Windows Authentication.</span></span> <span data-ttu-id="42f08-117">Se è necessario utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="42f08-117">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="42f08-118">Se è necessario archiviare le credenziali in un file script, è fondamentale proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="42f08-118">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="42f08-119">**-destinationserver** : nome del server nel quale vengono confrontati in dati, generalmente un Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="42f08-119">**-destinationserver** - name of the server on which the data is being compared, usually a Subscriber.</span></span>  
  
    -   <span data-ttu-id="42f08-120">**-destinationdatabase** : nome di un database da confrontare.</span><span class="sxs-lookup"><span data-stu-id="42f08-120">**-destinationdatabase** - name of a the database being compared.</span></span>  
  
    -   <span data-ttu-id="42f08-121">**-destinationtable** : nome della tabella da confrontare.</span><span class="sxs-lookup"><span data-stu-id="42f08-121">**-destinationtable** - name of the table being compared.</span></span>  
  
    -   <span data-ttu-id="42f08-122">(Facoltativo) **-destinationschema** : proprietario dello schema della tabella di destinazione, se diverso dallo schema predefinito.</span><span class="sxs-lookup"><span data-stu-id="42f08-122">(Optional) **-destinationschema** - schema owner of the destination table, if not the default schema.</span></span>  
  
    -   <span data-ttu-id="42f08-123">(Facoltativo) **-destinationuser** e **-destinationpassword** se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per la connessione al Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="42f08-123">(Optional) **-destinationuser** and **-destinationpassword** when using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication to connect to the Subscriber.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="42f08-124">Se possibile, usare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="42f08-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="42f08-125">Se è necessario utilizzare l'autenticazione di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , richiedere agli utenti di immettere le credenziali di sicurezza in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="42f08-125">If you must use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="42f08-126">Se è necessario archiviare le credenziali in un file script, è fondamentale proteggere il file per evitare accessi non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="42f08-126">If you must store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
    -   <span data-ttu-id="42f08-127">(Facoltativo) Utilizzare **-c** per eseguire un confronto a livello di colonna.</span><span class="sxs-lookup"><span data-stu-id="42f08-127">(Optional) Use **-c** to do a column-level comparison.</span></span>  
  
    -   <span data-ttu-id="42f08-128">(Facoltativo) Utilizzare **-q** per eseguire un confronto rapido del solo schema mediante conteggio delle righe.</span><span class="sxs-lookup"><span data-stu-id="42f08-128">(Optional) Use **-q** to do a fast, row count- and schema-only comparison.</span></span>  
  
    -   <span data-ttu-id="42f08-129">(Facoltativo) Specificare un nome file e un percorso per **-o** per restituire i risultati in un file.</span><span class="sxs-lookup"><span data-stu-id="42f08-129">(Optional) Specify a file name and path for **-o** to output the results to a file.</span></span>  
  
    -   <span data-ttu-id="42f08-130">(Facoltativo) Specificare una tabella nel database di sottoscrizione in cui inserire i risultati per **-et**.</span><span class="sxs-lookup"><span data-stu-id="42f08-130">(Optional) Specify a table in the subscription database into which to insert results for **-et**.</span></span> <span data-ttu-id="42f08-131">Se la tabella esiste già, è necessario eliminarla. A tale scopo, specificare **-dt** .</span><span class="sxs-lookup"><span data-stu-id="42f08-131">If the table already exists, specify **-dt** to first drop the table.</span></span>  
  
    -   <span data-ttu-id="42f08-132">(Facoltativo) Utilizzare **-f** per generare un file [!INCLUDE[tsql](../../../includes/tsql-md.md)] per correggere i dati nel Sottoscrittore e fare in modo che corrispondano a quelli nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-132">(Optional) Use **-f** to generate a [!INCLUDE[tsql](../../../includes/tsql-md.md)] file to fix data at the Subscriber so that it matches data at the Publisher.</span></span> <span data-ttu-id="42f08-133">Utilizzare **-df** per specificare il numero di istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] in ciascun file.</span><span class="sxs-lookup"><span data-stu-id="42f08-133">Use **-df** to specify the number of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements in each file.</span></span>  
  
    -   <span data-ttu-id="42f08-134">(Facoltativo) Utilizzare **-rc** e **-ri** per specificare il numero di tentativi di esecuzione di un'operazione e l'intervallo tra ogni tentativo.</span><span class="sxs-lookup"><span data-stu-id="42f08-134">(Optional) Use **-rc** and **-ri** to specify the number of times to retry an operation and the retry interval.</span></span>  
  
    -   <span data-ttu-id="42f08-135">(Facoltativo) Utilizzare **-strict** per imporre il confronto dello schema di tipo strict tra le tabelle di origine e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="42f08-135">(Optional) Use **-strict** to enforce strict schema comparison between source and destination tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f08-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42f08-136">See Also</span></span>  
 [<span data-ttu-id="42f08-137">Convalidare i dati nel Sottoscrittore</span><span class="sxs-lookup"><span data-stu-id="42f08-137">Validate Data at the Subscriber</span></span>](../validate-data-at-the-subscriber.md)  
  
  
