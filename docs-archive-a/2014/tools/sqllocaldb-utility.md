---
title: Utilità SqlLocalDB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- SqlLocalDB utility [SQL Server]
- local database runtime utility
- LocalDB, SqlLocalDB Utility
ms.assetid: d785cdb7-1ea0-4871-bde9-1ae7881190f5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bfb95cea4365d56c296d14fcc09046cd7eddc0c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711236"
---
# <a name="sqllocaldb-utility"></a><span data-ttu-id="3649d-102">Utilità SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="3649d-102">SqlLocalDB Utility</span></span>
  <span data-ttu-id="3649d-103">Utilizzare l' `SqlLocalDB` utilità per creare un'istanza del [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)] **database locale**.</span><span class="sxs-lookup"><span data-stu-id="3649d-103">Use the `SqlLocalDB` utility to create an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssExpCurrent](../includes/ssexpcurrent-md.md)]**LocalDB**.</span></span> <span data-ttu-id="3649d-104">L' `SqlLocalDB` utilità (SqlLocalDB.exe) è un semplice strumento da riga di comando che consente a utenti e sviluppatori di creare e gestire un'istanza del [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] **database locale**.</span><span class="sxs-lookup"><span data-stu-id="3649d-104">The `SqlLocalDB` utility (SqlLocalDB.exe) is a simple command line tool to enable users and developers to create and manage an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="3649d-105">Per informazioni sull'uso del **database locale**, vedere [SQL Server 2014 Express](../database-engine/configure-windows/sql-server-2016-express-localdb.md)local DB.</span><span class="sxs-lookup"><span data-stu-id="3649d-105">For information about how to use **LocalDB**, see [SQL Server 2014 Express LocalDB](../database-engine/configure-windows/sql-server-2016-express-localdb.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3649d-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3649d-106">Syntax</span></span>  
  
```  
SqlLocalDB.exe   
{  
      [ create   | c ] <instance-name><instance-version> [-s ]  
    | [ delete   | d ] <instance-name>  
    | [ start    | s ] <instance-name>  
    | [ stop     | p ] <instance-name>  [ -i ] [ -k ]  
    | [ share    | h ] ["<user_SID>" | "<user_account>" ] "<private-name>""<shared-name>"  
    | [ unshare  | u ] "<shared-name>"  
    | [ info     | i ] <instance-name>  
    | [ versions | v ]  
    | [ trace    | t ] [ on | off ]  
    | [ help     | -? ]  
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="3649d-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3649d-107">Arguments</span></span>  
 <span data-ttu-id="3649d-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [ **-s** ]</span><span class="sxs-lookup"><span data-stu-id="3649d-108">[ **create** | **c** ] *\<instance-name>* *\<instance-version>* [**-s** ]</span></span>  
 <span data-ttu-id="3649d-109">Crea una nuova istanza di **LocalDB** di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3649d-109">Creates a new of instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="3649d-110">`SqlLocalDB`Usa la versione dei [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] file binari specificati dall' *\<instance-version>* argomento.</span><span class="sxs-lookup"><span data-stu-id="3649d-110">`SqlLocalDB` uses the version of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] binaries specified by *\<instance-version>* argument.</span></span> <span data-ttu-id="3649d-111">Il numero di versione viene specificato in formato numerico con almeno un numero decimale.</span><span class="sxs-lookup"><span data-stu-id="3649d-111">The version number is specified in numeric format with at least one decimal.</span></span> <span data-ttu-id="3649d-112">I numeri di versione secondari (Service Pack) sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="3649d-112">The minor version numbers (service packs) are optional.</span></span> <span data-ttu-id="3649d-113">Ad esempio, i due numeri di versione seguenti sono entrambi accettabili: 11.0 o 11.0.1186.</span><span class="sxs-lookup"><span data-stu-id="3649d-113">For example the following two version numbers are both acceptable: 11.0, or 11.0.1186.</span></span> <span data-ttu-id="3649d-114">La versione specificata deve essere installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="3649d-114">The specified version must be installed on the computer.</span></span> <span data-ttu-id="3649d-115">Se non è specificato, il numero di versione viene impostato per impostazione predefinita sulla versione dell' `SqlLocalDB` utilità.</span><span class="sxs-lookup"><span data-stu-id="3649d-115">If not specified, the version number defaults to the version of the `SqlLocalDB` utility.</span></span> <span data-ttu-id="3649d-116">Aggiungere **-s** per avviare la nuova istanza di **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="3649d-116">Adding **-s** starts the new instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="3649d-117">[ **share** | **h** ]</span><span class="sxs-lookup"><span data-stu-id="3649d-117">[ **share** | **h** ]</span></span>  
 <span data-ttu-id="3649d-118">Condivide l'istanza privata specificata di **LocalDB** tramite il nome condiviso indicato.</span><span class="sxs-lookup"><span data-stu-id="3649d-118">Shares the specified private instance of **LocalDB** using the specified shared name.</span></span> <span data-ttu-id="3649d-119">Se viene omesso il SID dell'utente o il nome dell'account, il valore predefinito è l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="3649d-119">If the user SID or account name is omitted, it defaults to the current user.</span></span>  
  
 <span data-ttu-id="3649d-120">[ **unshared** | **u** ]</span><span class="sxs-lookup"><span data-stu-id="3649d-120">[ **unshared** | **u** ]</span></span>  
 <span data-ttu-id="3649d-121">Arresta la condivisione dell'istanza condivisa specificata di **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="3649d-121">Stops the sharing of the specified shared instance of **LocalDB**.</span></span>  
  
 <span data-ttu-id="3649d-122">[ **delete** | **d** ] *\<instance-name>*</span><span class="sxs-lookup"><span data-stu-id="3649d-122">[ **delete** | **d** ] *\<instance-name>*</span></span>  
 <span data-ttu-id="3649d-123">Elimina l'istanza specificata di **LocalDB** di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3649d-123">Deletes the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span>  
  
 <span data-ttu-id="3649d-124">[ **start** | **s** ] " *\<instance-name>* "</span><span class="sxs-lookup"><span data-stu-id="3649d-124">[ **start** | **s** ] "*\<instance-name>*"</span></span>  
 <span data-ttu-id="3649d-125">Avvia l'istanza specificata di **LocalDB** di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3649d-125">Starts the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="3649d-126">Quando ha esito positivo, l'istruzione restituisce l'indirizzo della named pipe del **database locale**.</span><span class="sxs-lookup"><span data-stu-id="3649d-126">When successful the statement returns the named pipe address of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="3649d-127">[ **stop** | **p** ] *\<instance-name>* [ **-i** ] [ **-k** ]</span><span class="sxs-lookup"><span data-stu-id="3649d-127">[ **stop** | **p** ] *\<instance-name>* [**-i** ] [**-k** ]</span></span>  
 <span data-ttu-id="3649d-128">Arresta l'istanza specificata di **LocalDB** di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3649d-128">Stops the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**.</span></span> <span data-ttu-id="3649d-129">L'aggiunta di **-i** richiede l'arresto dell'istanza con l' `NOWAIT` opzione.</span><span class="sxs-lookup"><span data-stu-id="3649d-129">Adding **-i** requests the instance shutdown with the `NOWAIT` option.</span></span> <span data-ttu-id="3649d-130">Aggiungere **-k** per terminare il processo dell'istanza senza contattarlo.</span><span class="sxs-lookup"><span data-stu-id="3649d-130">Adding **-k** kills the instance process without contacting it.</span></span>  
  
 <span data-ttu-id="3649d-131">[ **info** | **i** ] [ *\<instance-name>* ]</span><span class="sxs-lookup"><span data-stu-id="3649d-131">[ **info** | **i** ] [ *\<instance-name>* ]</span></span>  
 <span data-ttu-id="3649d-132">Elenca tutte le istanze di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** di proprietà dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="3649d-132">Lists all instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** owned by the current user.</span></span>  
  
 <span data-ttu-id="3649d-133">*\<instance-name>* restituisce il nome, la versione, lo stato (In esecuzione o Arrestato), l'ultima ora di inizio per l'istanza specificata di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** e il nome della pipe locale di **LocalDB**.</span><span class="sxs-lookup"><span data-stu-id="3649d-133">*\<instance-name>* returns the name, version, state (Running or Stopped), last start time for the specified instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB**, and the local pipe name of the **LocalDB**.</span></span>  
  
 <span data-ttu-id="3649d-134">[ **trace** | **t** ] **on** | **off**</span><span class="sxs-lookup"><span data-stu-id="3649d-134">[ **trace** | **t** ] **on** | **off**</span></span>  
 <span data-ttu-id="3649d-135">**Trace on** Abilita la traccia per le `SqlLocalDB` chiamate API per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="3649d-135">**trace on** enables tracing for the `SqlLocalDB` API calls for the current user.</span></span> <span data-ttu-id="3649d-136">**trace off** disabilita la traccia.</span><span class="sxs-lookup"><span data-stu-id="3649d-136">**trace off** disables tracing.</span></span>  
  
 <span data-ttu-id="3649d-137">**-?**</span><span class="sxs-lookup"><span data-stu-id="3649d-137">**-?**</span></span>  
 <span data-ttu-id="3649d-138">Restituisce brevi descrizioni di ogni `SqlLocalDB` opzione.</span><span class="sxs-lookup"><span data-stu-id="3649d-138">Returns brief descriptions of each `SqlLocalDB` option.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3649d-139">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3649d-139">Remarks</span></span>  
 <span data-ttu-id="3649d-140">L'argomento *instance name* deve seguire le regole per gli identificatori di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oppure deve essere incluso tra virgolette.</span><span class="sxs-lookup"><span data-stu-id="3649d-140">The *instance name* argument must follow the rules for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifiers or it must be enclosed in double quotes.</span></span>  
  
 <span data-ttu-id="3649d-141">L'esecuzione di SqlLocalDB senza argomenti restituisce il testo della Guida.</span><span class="sxs-lookup"><span data-stu-id="3649d-141">Executing SqlLocalDB without arguments returns the help text.</span></span>  
  
 <span data-ttu-id="3649d-142">Le operazioni diverse dall'avvio possono essere eseguite solo su un'istanza che appartiene all'utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="3649d-142">Operations other than start can only be performed on an instance belonging to currently logged in user.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3649d-143">Esempi</span><span class="sxs-lookup"><span data-stu-id="3649d-143">Examples</span></span>  
  
### <a name="a-creating-an-instance-of-localdb"></a><span data-ttu-id="3649d-144">R.</span><span class="sxs-lookup"><span data-stu-id="3649d-144">A.</span></span> <span data-ttu-id="3649d-145">Creazione di un'istanza di LocalDB.</span><span class="sxs-lookup"><span data-stu-id="3649d-145">Creating an Instance of LocalDB</span></span>  
 <span data-ttu-id="3649d-146">L'esempio seguente crea e avvia un'istanza di [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**di** denominata `DEPARTMENT` usando i file binari di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3649d-146">The following example creates an instance of [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]**LocalDB** named `DEPARTMENT` using the [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] binaries and starts the instance.</span></span>  
  
```  
SqlLocalDB.exe create "DEPARTMENT" 12.0 -s  
```  
  
### <a name="b-working-with-a-shared-instance-of-localdb"></a><span data-ttu-id="3649d-147">B.</span><span class="sxs-lookup"><span data-stu-id="3649d-147">B.</span></span> <span data-ttu-id="3649d-148">Utilizzo di un'istanza condivisa di LocalDB</span><span class="sxs-lookup"><span data-stu-id="3649d-148">Working with a Shared Instance of LocalDB</span></span>  
 <span data-ttu-id="3649d-149">Aprire un prompt dei comandi con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="3649d-149">Open a command prompt using Administrator privileges.</span></span>  
  
```  
SqlLocalDB.exe create "DeptLocalDB"  
SqlLocalDB.exe share "DeptLocalDB" "DeptSharedLocalDB"  
SqlLocalDB.exe start "DeptLocalDB"  
SqlLocalDB.exe info "DeptLocalDB"  
REM The previous statement outputs the Instance pipe name for the next step  
sqlcmd -S np:\\.\pipe\LOCALDB#<use your pipe name>\tsql\query  
CREATE LOGIN NewLogin WITH PASSWORD = 'Passw0rd!!@52';   
GO  
CREATE USER NewLogin;  
GO  
EXIT  
```  
  
 <span data-ttu-id="3649d-150">Eseguire il codice riportato di seguito per connettersi all'istanza condivisa di **LocalDB** utilizzando l'account di accesso `NewLogin` .</span><span class="sxs-lookup"><span data-stu-id="3649d-150">Execute the following code to connect to the shared instance of **LocalDB** using the `NewLogin` login.</span></span>  
  
```  
sqlcmd -S (localdb)\.\DeptSharedLocalDB -U NewLogin -P Passw0rd!!@52  
```  
  
## <a name="see-also"></a><span data-ttu-id="3649d-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3649d-151">See Also</span></span>  
 [<span data-ttu-id="3649d-152">SQL Server 2014 Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="3649d-152">SQL Server 2014 Express LocalDB</span></span>](../database-engine/configure-windows/sql-server-2016-express-localdb.md)  
  
  
