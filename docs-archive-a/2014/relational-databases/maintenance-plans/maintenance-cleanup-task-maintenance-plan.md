---
title: Attività Pulizia file manutenzione (Piano di manutenzione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.maint.cleanup.f1
helpviewer_keywords:
- Maintenance Cleanup Task dialog box
ms.assetid: 022b679c-6799-4c13-9185-814224a20412
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9023881ff5cf5ba5ddd8c61aa179c5881162bf44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629382"
---
# <a name="maintenance-cleanup-task-maintenance-plan"></a><span data-ttu-id="be93b-102">Attività Pulizia file manutenzione (Piano di manutenzione)</span><span class="sxs-lookup"><span data-stu-id="be93b-102">Maintenance Cleanup Task (Maintenance Plan)</span></span>
  <span data-ttu-id="be93b-103">Usare l' **Attività Pulizia file di manutenzione** per rimuovere file obsoleti correlati ai piani di manutenzione, inclusi i report in formato testo creati dai piani di manutenzione e i file di backup del database.</span><span class="sxs-lookup"><span data-stu-id="be93b-103">Use the **Maintenance Cleanup Task** to remove old files related to maintenance plans, including text reports created by maintenance plans and database backup files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be93b-104">L'attività Pulizia file manutenzione non elimina automaticamente i file nelle sottocartelle della directory specificata.</span><span class="sxs-lookup"><span data-stu-id="be93b-104">The Maintenance Cleanup task does not automatically delete files in the subfolders of the specified directory.</span></span> <span data-ttu-id="be93b-105">Questa caratteristica riduce la possibilità di un attacco dannoso che utilizzi l'attività Pulizia file manutenzione per eliminare i file.</span><span class="sxs-lookup"><span data-stu-id="be93b-105">This feature reduces the possibility of a malicious attack that uses the Maintenance Cleanup task to delete files.</span></span> <span data-ttu-id="be93b-106">Per eliminare i file nelle sottocartelle di primo livello è necessario selezionare **Includi sottocartelle di primo livello**.</span><span class="sxs-lookup"><span data-stu-id="be93b-106">If you want to delete files in first-level subfolders, you must select **Include first-level subfolders**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be93b-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="be93b-107">Options</span></span>  
 <span data-ttu-id="be93b-108">**Connection**</span><span class="sxs-lookup"><span data-stu-id="be93b-108">**Connection**</span></span>  
 <span data-ttu-id="be93b-109">Consente di visualizzare la connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="be93b-109">Displays the current connection.</span></span>  
  
 <span data-ttu-id="be93b-110">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="be93b-110">**New**</span></span>  
 <span data-ttu-id="be93b-111">Consente di creare una nuova connessione server da utilizzare per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="be93b-111">Create a new server connection to use when performing this task.</span></span> <span data-ttu-id="be93b-112">La finestra di dialogo **Nuova connessione** è descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="be93b-112">The **New Connection** dialog box is described below.</span></span>  
  
 <span data-ttu-id="be93b-113">**File di backup**</span><span class="sxs-lookup"><span data-stu-id="be93b-113">**Backup files**</span></span>  
 <span data-ttu-id="be93b-114">Consente di eliminare i file di backup.</span><span class="sxs-lookup"><span data-stu-id="be93b-114">Delete backup files.</span></span>  
  
 <span data-ttu-id="be93b-115">**Report in formato testo piano di manutenzione**</span><span class="sxs-lookup"><span data-stu-id="be93b-115">**Maintenance Plan text reports**</span></span>  
 <span data-ttu-id="be93b-116">Elimina i report in formato testo relativi a piani di manutenzione eseguiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="be93b-116">Delete text reports of previously run maintenance plans.</span></span>  
  
 <span data-ttu-id="be93b-117">**Elimina file specifico**</span><span class="sxs-lookup"><span data-stu-id="be93b-117">**Delete specific file**</span></span>  
 <span data-ttu-id="be93b-118">Consente di eliminare il file specifico indicato nella casella **Nome file** .</span><span class="sxs-lookup"><span data-stu-id="be93b-118">Delete the specific file provided in the **File name** box.</span></span>  
  
 <span data-ttu-id="be93b-119">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="be93b-119">**File name**</span></span>  
 <span data-ttu-id="be93b-120">Percorso e nome del file da eliminare.</span><span class="sxs-lookup"><span data-stu-id="be93b-120">Path and name of the file to be deleted.</span></span>  
  
 <span data-ttu-id="be93b-121">**Cerca nella cartella ed elimina i file in base all'estensione**</span><span class="sxs-lookup"><span data-stu-id="be93b-121">**Search folder and delete files based on an extension**</span></span>  
 <span data-ttu-id="be93b-122">Consente di eliminare tutti i file con l'estensione specificata contenuti nella cartella indicata.</span><span class="sxs-lookup"><span data-stu-id="be93b-122">Delete all files with the specified extension in the specified folder.</span></span> <span data-ttu-id="be93b-123">Utilizzare questa opzione per eliminare più file contemporaneamente, ad esempio tutti i file di backup con estensione bak contenuti nella cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="be93b-123">Use this to delete multiple files at once, such as all backup files with the .bak extension, in the Tuesday folder.</span></span>  
  
 <span data-ttu-id="be93b-124">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="be93b-124">**Folder**</span></span>  
 <span data-ttu-id="be93b-125">Percorso e nome della cartella contenente i file da eliminare.</span><span class="sxs-lookup"><span data-stu-id="be93b-125">Path and name of the folder containing the files to be deleted.</span></span>  
  
 <span data-ttu-id="be93b-126">**Estensione file**</span><span class="sxs-lookup"><span data-stu-id="be93b-126">**File extension**</span></span>  
 <span data-ttu-id="be93b-127">Indica l'estensione dei file da eliminare.</span><span class="sxs-lookup"><span data-stu-id="be93b-127">Provide the file extension of the files to be deleted.</span></span>  
  
 <span data-ttu-id="be93b-128">**Includi sottocartelle di primo livello**</span><span class="sxs-lookup"><span data-stu-id="be93b-128">**Include first-level subfolders**</span></span>  
 <span data-ttu-id="be93b-129">Consente di eliminare i file con l'estensione specificata in **Estensione file** dalle sottocartelle di primo livello in **Cartella**.</span><span class="sxs-lookup"><span data-stu-id="be93b-129">Delete files with the extension specified for **File extension** from first-level subfolders under **Folder**.</span></span>  
  
 <span data-ttu-id="be93b-130">**Elimina i file in base alla data del file al momento dell'esecuzione dell'attività**</span><span class="sxs-lookup"><span data-stu-id="be93b-130">**Delete files based on the age of the file at task run time**</span></span>  
 <span data-ttu-id="be93b-131">Specificare il periodo di memorizzazione minimo trascorso il quale i file verranno eliminati, indicando un numero e un'unità di tempo nella casella **Elimina i file con data anteriore a** .</span><span class="sxs-lookup"><span data-stu-id="be93b-131">Specify the minimum age of the files that you want to delete by providing a number, and unit of time in the **Delete files older than the following** box.</span></span>  
  
 <span data-ttu-id="be93b-132">**Elimina i file con data anteriore a**</span><span class="sxs-lookup"><span data-stu-id="be93b-132">**Delete files older than the following**</span></span>  
 <span data-ttu-id="be93b-133">Consente di specificare la data minima dei file da eliminare indicando un numero e un'unità di tempo (giorno/i, settimana/e, mese/i o anno/i).</span><span class="sxs-lookup"><span data-stu-id="be93b-133">Specify the minimum age of the files that you want to delete by providing a number, and unit of time (Day, Week, Month, or Year).</span></span> <span data-ttu-id="be93b-134">I file con data anteriore alla data specificata verranno eliminati.</span><span class="sxs-lookup"><span data-stu-id="be93b-134">Files older than the time frame specified will be deleted.</span></span>  
  
 <span data-ttu-id="be93b-135">**Visualizza codice T-SQL**</span><span class="sxs-lookup"><span data-stu-id="be93b-135">**View T-SQL**</span></span>  
 <span data-ttu-id="be93b-136">Consente di visualizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] eseguite sul server per questa attività, in base alle opzioni selezionate.</span><span class="sxs-lookup"><span data-stu-id="be93b-136">View the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements performed against the server for this task, based on the selected options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be93b-137">Se il numero di oggetti interessato dall'attività è elevato, la visualizzazione del codice potrebbe richiedere una considerevole quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="be93b-137">When the number of objects affected is large, this display can take a considerable amount of time.</span></span>  
  
## <a name="new-connection-dialog-box"></a><span data-ttu-id="be93b-138">Finestra di dialogo Nuova connessione</span><span class="sxs-lookup"><span data-stu-id="be93b-138">New Connection Dialog Box</span></span>  
 <span data-ttu-id="be93b-139">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="be93b-139">**Connection name**</span></span>  
 <span data-ttu-id="be93b-140">Consente di immettere un nome per la nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="be93b-140">Enter a name for the new connection.</span></span>  
  
 <span data-ttu-id="be93b-141">**Selezionare o immettere il nome di un server**</span><span class="sxs-lookup"><span data-stu-id="be93b-141">**Select or enter a server name**</span></span>  
 <span data-ttu-id="be93b-142">Consente di selezionare il server a cui connettersi per l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="be93b-142">Select a server to connect to when performing this task.</span></span>  
  
 <span data-ttu-id="be93b-143">**...**</span><span class="sxs-lookup"><span data-stu-id="be93b-143">**...**</span></span>  
 <span data-ttu-id="be93b-144">Consente di visualizzare l'elenco dei server disponibili.</span><span class="sxs-lookup"><span data-stu-id="be93b-144">Select to view the list of available servers.</span></span>  
  
 <span data-ttu-id="be93b-145">**Immettere le informazioni per l'accesso al server**</span><span class="sxs-lookup"><span data-stu-id="be93b-145">**Enter information to log on to the server**</span></span>  
 <span data-ttu-id="be93b-146">Consente di specificare le opzioni di autenticazione per l'accesso al server.</span><span class="sxs-lookup"><span data-stu-id="be93b-146">Specify how to authenticate against the server.</span></span>  
  
 <span data-ttu-id="be93b-147">**Usa la sicurezza integrata di Windows NT**</span><span class="sxs-lookup"><span data-stu-id="be93b-147">**Use Windows integrated security**</span></span>  
 <span data-ttu-id="be93b-148">Consente di connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizzando l'autenticazione di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="be93b-148">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with Microsoft Windows Authentication.</span></span>  
  
 <span data-ttu-id="be93b-149">**Usa nome utente e password specifici**</span><span class="sxs-lookup"><span data-stu-id="be93b-149">**Use a specific user name and password**</span></span>  
 <span data-ttu-id="be93b-150">Consente di connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] utilizzando l'autenticazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="be93b-150">Connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] using SQL Server Authentication.</span></span> <span data-ttu-id="be93b-151">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="be93b-151">This option is not available.</span></span>  
  
 <span data-ttu-id="be93b-152">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="be93b-152">**User name**</span></span>  
 <span data-ttu-id="be93b-153">Consente di specificare un account di accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="be93b-153">Provide a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to use when authenticating.</span></span> <span data-ttu-id="be93b-154">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="be93b-154">This option is not available.</span></span>  
  
 <span data-ttu-id="be93b-155">**Password**</span><span class="sxs-lookup"><span data-stu-id="be93b-155">**Password**</span></span>  
 <span data-ttu-id="be93b-156">Consente di specificare una password da utilizzare per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="be93b-156">Provide a password to use when authenticating.</span></span> <span data-ttu-id="be93b-157">Questa opzione non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="be93b-157">This option is not available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be93b-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be93b-158">See Also</span></span>  
 [<span data-ttu-id="be93b-159">Piani di manutenzione</span><span class="sxs-lookup"><span data-stu-id="be93b-159">Maintenance Plans</span></span>](maintenance-plans.md)  
  
  
