---
title: 'Strumento di gestione della riga di comando: SqlLocalDB.exe | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: dd0882b1-a8a9-447a-8bdf-0f9d7f36d336
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d21a6a8879e981e52bd2e7d3bd05a37e65d8cf4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624733"
---
# <a name="command-line-management-tool-sqllocaldbexe"></a><span data-ttu-id="67f31-102">Strumento di gestione della riga di comando: SqlLocalDB.exe</span><span class="sxs-lookup"><span data-stu-id="67f31-102">Command-Line Management Tool: SqlLocalDB.exe</span></span>
  <span data-ttu-id="67f31-103">SqlLocalDB.exe è uno strumento semplice che consente all'utente di gestire facilmente le istanze del database locale dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="67f31-103">SqlLocalDB.exe is a simple tool that enables the user to easily manage LocalDB instances from the command line.</span></span> <span data-ttu-id="67f31-104">Viene implementato come un semplice wrapper dell'API dell'istanza del database locale.</span><span class="sxs-lookup"><span data-stu-id="67f31-104">It is implemented as a simple wrapper around the LocalDB instance API.</span></span> <span data-ttu-id="67f31-105">Come in molti strumenti SQL Server simili, ad esempio SQLCMD, i parametri vengono passati a SqlLocalDB come argomenti della riga di comando e l'output viene inviato alla console.</span><span class="sxs-lookup"><span data-stu-id="67f31-105">As in many similar SQL Server tools (for example, SQLCMD), parameters are passed to SqlLocalDB as command-line arguments and output is sent to the console.</span></span>  
  
 <span data-ttu-id="67f31-106">SqlLocalDB consente agli sviluppatori di utilizzare il database locale senza la necessità di scrivere codice per chiamare l'API o dipendere da altri strumenti per effettuare tale operazione.</span><span class="sxs-lookup"><span data-stu-id="67f31-106">SqlLocalDB enables developers to use LocalDB without having to write code to call the API or depend on other tools to do it for them.</span></span>  
  
## <a name="sqllocaldb-options"></a><span data-ttu-id="67f31-107">Opzioni di SqlLocalDB</span><span class="sxs-lookup"><span data-stu-id="67f31-107">SqlLocalDB Options</span></span>  
 <span data-ttu-id="67f31-108">SqlLocalDB supporta le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="67f31-108">SqlLocalDB supports the following options.</span></span>  
  
|<span data-ttu-id="67f31-109">Opzione</span><span class="sxs-lookup"><span data-stu-id="67f31-109">Option</span></span>|<span data-ttu-id="67f31-110">Funzione</span><span class="sxs-lookup"><span data-stu-id="67f31-110">What it does</span></span>|  
|------------|------------------|  
|`-?`|<span data-ttu-id="67f31-111">Viene stampato il testo della Guida.</span><span class="sxs-lookup"><span data-stu-id="67f31-111">Prints help text.</span></span>|  
|`create&#124;c "instance name" [version-number] [-s]`|<span data-ttu-id="67f31-112">Viene creata una nuova istanza del database locale con una versione e un nome specificati.</span><span class="sxs-lookup"><span data-stu-id="67f31-112">Creates a new LocalDB instance with a specified name and version.</span></span><br /><br /> <span data-ttu-id="67f31-113">Se il parametro [version-number] viene omesso, il valore predefinito è la versione della build di SqlLocalDB.</span><span class="sxs-lookup"><span data-stu-id="67f31-113">If the [version-number] parameter is omitted, it defaults to the SqlLocalDB build version.</span></span><br /><br /> <span data-ttu-id="67f31-114">Tramite il parametro -s viene avviata la nuova istanza del database locale dopo la relativa creazione.</span><span class="sxs-lookup"><span data-stu-id="67f31-114">-s starts the new LocalDB instance after it is created.</span></span>|  
|`delete&#124;d "instance name"`|<span data-ttu-id="67f31-115">Viene eliminata l'istanza del database locale con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="67f31-115">Deletes the LocalDB instance with the specified name.</span></span>|  
|`start&#124;s "instance name"`|<span data-ttu-id="67f31-116">Viene avviata l'istanza del database locale con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="67f31-116">Starts the LocalDB instance with the specified name.</span></span>|  
|`stop&#124;p "instance name" [-i&#124;-k]`|<span data-ttu-id="67f31-117">Viene arrestata l'istanza del database locale con il nome specificato, al termine dell'esecuzione delle query correnti.</span><span class="sxs-lookup"><span data-stu-id="67f31-117">Stops the LocalDB instance with the specified name, after current queries finish running.</span></span><br /><br /> <span data-ttu-id="67f31-118">Tramite il parametro -i viene richiesto l'arresto dell'istanza del database locale con l'opzione NOWAIT.</span><span class="sxs-lookup"><span data-stu-id="67f31-118">-i requests the LocalDB instance shutdown with the NOWAIT option.</span></span><br /><br /> <span data-ttu-id="67f31-119">Tramite il parametro -k viene terminato il processo dell'istanza del database locale senza contattare quest'ultimo.</span><span class="sxs-lookup"><span data-stu-id="67f31-119">-k kills the LocalDB instance process without contacting it.</span></span>|  
|`share&#124;h ["owner SID or account"] "private name" "shared name"`|<span data-ttu-id="67f31-120">Viene condivisa l'istanza privata specificata tramite il nome condiviso indicato.</span><span class="sxs-lookup"><span data-stu-id="67f31-120">Shares the specified private instance using the specified shared name.</span></span> <span data-ttu-id="67f31-121">Se viene omesso il SID dell'utente o il nome dell'account, il valore predefinito è l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="67f31-121">If the user SID or account name is omitted, it defaults to the current user.</span></span>|  
|`unshare&#124;u "shared name"`|<span data-ttu-id="67f31-122">Viene rimossa la condivisione dell'istanza del database locale condivisa specificata.</span><span class="sxs-lookup"><span data-stu-id="67f31-122">Unshares the specified shared LocalDB instance.</span></span>|  
|`info&#124;i`|<span data-ttu-id="67f31-123">Vengono elencate tutte le istanze del database locale esistenti di proprietà dell'utente corrente nonché tutte le istanze del database locale condivise.</span><span class="sxs-lookup"><span data-stu-id="67f31-123">Lists all existing LocalDB instances that are owned by the current user and all shared LocalDB instances.</span></span>|  
|`info&#124;i "instance name"`|<span data-ttu-id="67f31-124">Vengono stampate le informazioni sull'istanza specificata del database locale.</span><span class="sxs-lookup"><span data-stu-id="67f31-124">Prints the information about the specified LocalDB instance.</span></span>|  
|`versions&#124;v`|<span data-ttu-id="67f31-125">Vengono elencate tutte le versioni del database locale installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="67f31-125">Lists all LocalDB versions installed on the computer.</span></span>|  
|||  
|`trace&#124;t on&#124;off`|<span data-ttu-id="67f31-126">Viene abilitata o disabilitata la traccia.</span><span class="sxs-lookup"><span data-stu-id="67f31-126">Turns tracing on and off.</span></span>|  
  
 <span data-ttu-id="67f31-127">Gli spazi in SqlLocalDB vengono considerati come delimitatori. È necessario racchiudere tra virgolette i nomi delle istanze contenenti spazi e caratteri speciali.</span><span class="sxs-lookup"><span data-stu-id="67f31-127">SqlLocalDB treats spaces as delimiters; you must surround the instance names that contain spaces and special characters with quotes.</span></span> <span data-ttu-id="67f31-128">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67f31-128">For example:</span></span>  
  
 `SqlLocalDB create "My instance name with spaces"`  
  
  
