---
title: Editor attività Trasferisci account di accesso (pagina account di accesso) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferloginstask.logins.f1
helpviewer_keywords:
- Transfer Logins Task Editor
ms.assetid: bf244c24-bd45-4ece-b66b-78b488f35c5b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b33fea6c78df75b7eebe8987f952dce33bdc4407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638456"
---
# <a name="transfer-logins-task-editor-logins-page"></a><span data-ttu-id="4da6f-102">Editor attività Trasferisci account di accesso (pagina Account di accesso)</span><span class="sxs-lookup"><span data-stu-id="4da6f-102">Transfer Logins Task Editor (Logins Page)</span></span>
  <span data-ttu-id="4da6f-103">Usare la pagina **Account di accesso** della finestra di dialogo **Editor attività Trasferisci account di accesso** per impostare le proprietà per la copia di uno o più account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a un altra.</span><span class="sxs-lookup"><span data-stu-id="4da6f-103">Use the **Logins** page of the **Transfer Logins Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="4da6f-104">Per altre informazioni su questa attività, vedere [Attività Trasferisci account di accesso](control-flow/transfer-logins-task.md).</span><span class="sxs-lookup"><span data-stu-id="4da6f-104">For more information about this task, see [Transfer Logins Task](control-flow/transfer-logins-task.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4da6f-105">Durante l'esecuzione di questa attività, sul server di destinazione vengono creati gli account di accesso con password casuali e le password vengono disabilitate.</span><span class="sxs-lookup"><span data-stu-id="4da6f-105">When the Transfer Logins task is executed, logins are created on the destination server with random passwords and the passwords are disabled.</span></span> <span data-ttu-id="4da6f-106">Per usare questi account di accesso, è necessario che un membro del ruolo predefinito del server **sysadmin** cambi le password e quindi le attivi.</span><span class="sxs-lookup"><span data-stu-id="4da6f-106">To use these logins, a member of the **sysadmin** fixed server role must change the passwords and then enable them.</span></span> <span data-ttu-id="4da6f-107">L'account di accesso **sa** non può essere trasferito.</span><span class="sxs-lookup"><span data-stu-id="4da6f-107">The **sa** login cannot be transferred.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4da6f-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4da6f-108">Options</span></span>  
 <span data-ttu-id="4da6f-109">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="4da6f-109">**SourceConnection**</span></span>  
 <span data-ttu-id="4da6f-110">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="4da6f-110">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="4da6f-111">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="4da6f-111">**DestinationConnection**</span></span>  
 <span data-ttu-id="4da6f-112">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-112">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="4da6f-113">**LoginsToTransfer**</span><span class="sxs-lookup"><span data-stu-id="4da6f-113">**LoginsToTransfer**</span></span>  
 <span data-ttu-id="4da6f-114">Consente di selezionare gli account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da copiare dal server di origine a quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-114">Select the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins to copy from the source to the destination server.</span></span> <span data-ttu-id="4da6f-115">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4da6f-115">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="4da6f-116">valore</span><span class="sxs-lookup"><span data-stu-id="4da6f-116">Value</span></span>|<span data-ttu-id="4da6f-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4da6f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da6f-118">**AllLogins**</span><span class="sxs-lookup"><span data-stu-id="4da6f-118">**AllLogins**</span></span>|<span data-ttu-id="4da6f-119">Tutti gli account di accesso di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nel server di origine verranno copiati in quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-119">All [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] logins on the source server will be copied to the destination server.</span></span>|  
|<span data-ttu-id="4da6f-120">**SelectedLogins**</span><span class="sxs-lookup"><span data-stu-id="4da6f-120">**SelectedLogins**</span></span>|<span data-ttu-id="4da6f-121">Solo gli account di accesso specificati in **LoginsList** verranno copiati nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-121">Only logins specified with **LoginsList** will be copied to the destination server.</span></span>|  
|<span data-ttu-id="4da6f-122">**AllLoginsFromSelectedDatabases**</span><span class="sxs-lookup"><span data-stu-id="4da6f-122">**AllLoginsFromSelectedDatabases**</span></span>|<span data-ttu-id="4da6f-123">Tutti gli account di accesso nel database specificato in **DatabasesList** verranno copiati nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-123">All logins from the databases specified with **DatabasesList** will be copied to the destination server.</span></span>|  
  
 <span data-ttu-id="4da6f-124">**LoginsList**</span><span class="sxs-lookup"><span data-stu-id="4da6f-124">**LoginsList**</span></span>  
 <span data-ttu-id="4da6f-125">Consente di selezionare gli account di accesso nel server di origine da copiare in quello di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-125">Select the logins on the source server to be copied to the destination server.</span></span> <span data-ttu-id="4da6f-126">Questa opzione è disponibile solo se è selezionata **SelectedLogins** per **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="4da6f-126">This option is only available when **SelectedLogins** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="4da6f-127">**DatabasesList**</span><span class="sxs-lookup"><span data-stu-id="4da6f-127">**DatabasesList**</span></span>  
 <span data-ttu-id="4da6f-128">Consente di selezionare i database nel server di origine contenenti gli account di accesso da copiare sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-128">Select the databases on the source server that contain logins to be copied to the destination server.</span></span> <span data-ttu-id="4da6f-129">Questa opzione è disponibile solo se è selezionata **AllLoginsFromSelectedDatabases** per **LoginsToTransfer**.</span><span class="sxs-lookup"><span data-stu-id="4da6f-129">This option is only available when **AllLoginsFromSelectedDatabases** is selected for **LoginsToTransfer**.</span></span>  
  
 <span data-ttu-id="4da6f-130">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="4da6f-130">**IfObjectExists**</span></span>  
 <span data-ttu-id="4da6f-131">Consente di selezionare la modalità di gestione dei nomi già esistenti nel server di destinazione da parte dell'attività</span><span class="sxs-lookup"><span data-stu-id="4da6f-131">Select how the task should handle logins of the same name that already exist on the destination server.</span></span>  
  
 <span data-ttu-id="4da6f-132">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4da6f-132">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="4da6f-133">valore</span><span class="sxs-lookup"><span data-stu-id="4da6f-133">Value</span></span>|<span data-ttu-id="4da6f-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4da6f-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4da6f-135">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="4da6f-135">**FailTask**</span></span>|<span data-ttu-id="4da6f-136">L'attività ha esito negativo se esistono già account di accesso con lo stesso nome nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-136">Task fails if logins of the same name already exist on the destination server.</span></span>|  
|<span data-ttu-id="4da6f-137">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="4da6f-137">**Overwrite**</span></span>|<span data-ttu-id="4da6f-138">L'attività sovrascrive gli account di accesso con lo stesso nome nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-138">Task overwrites logins of the same name on the destination server.</span></span>|  
|<span data-ttu-id="4da6f-139">**Skip**</span><span class="sxs-lookup"><span data-stu-id="4da6f-139">**Skip**</span></span>|<span data-ttu-id="4da6f-140">L'attività ignora gli account di accesso con lo stesso nome nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-140">Task skips logins of the same name that exist on the destination server.</span></span>|  
  
 <span data-ttu-id="4da6f-141">**CopySids**</span><span class="sxs-lookup"><span data-stu-id="4da6f-141">**CopySids**</span></span>  
 <span data-ttu-id="4da6f-142">Consente di indicare se gli identificatori di sicurezza associati agli account di accesso devono essere copiati sul server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4da6f-142">Select whether the security identifiers associated with the logins should be copied to the destination server.</span></span> <span data-ttu-id="4da6f-143">L'opzione**CopySids** deve essere impostata su **True** se l'attività Trasferisci account di accesso viene usata contestualmente all'attività Trasferisci database.</span><span class="sxs-lookup"><span data-stu-id="4da6f-143">**CopySids** must be set to **True** if the Transfer Logins task is used along with the Transfer Database task.</span></span> <span data-ttu-id="4da6f-144">In caso contrario, gli account di accesso copiati non verranno riconosciuti dal database trasferito.</span><span class="sxs-lookup"><span data-stu-id="4da6f-144">Otherwise, the copied logins will not be recognized by the transferred database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da6f-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4da6f-145">See Also</span></span>  
 <span data-ttu-id="4da6f-146">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-146">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4da6f-147">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-147">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="4da6f-148">[Editor attività Trasferisci account di accesso &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-148">[Transfer Logins Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="4da6f-149">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-149">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="4da6f-150">[Gestione connessione SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-150">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="4da6f-151">[Password complesse](../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="4da6f-151">[Strong Passwords](../relational-databases/security/strong-passwords.md) </span></span>  
 [<span data-ttu-id="4da6f-152">Considerazioni sulla sicurezza per un'installazione di SQL Server</span><span class="sxs-lookup"><span data-stu-id="4da6f-152">Security Considerations for a SQL Server Installation</span></span>](../../2014/sql-server/install/security-considerations-for-a-sql-server-installation.md)  
  
  
