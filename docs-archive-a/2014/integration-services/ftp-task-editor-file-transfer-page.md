---
title: Editor attività FTP (pagina trasferimento file) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.filetransfer.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 37e52220-feb2-474c-ad88-fa1b1059acd4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8094051e93c4165be6ae186bde394f9271d60669
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626152"
---
# <a name="ftp-task-editor-file-transfer-page"></a><span data-ttu-id="feb38-102">Editor attività FTP (pagina Trasferimento file)</span><span class="sxs-lookup"><span data-stu-id="feb38-102">FTP Task Editor (File Transfer Page)</span></span>
  <span data-ttu-id="feb38-103">Usare la pagina **Trasferimento file** della finestra di dialogo **Editor attività FTP** per configurare l'operazione FTP eseguita dall'attività.</span><span class="sxs-lookup"><span data-stu-id="feb38-103">Use the **File Transfer** page of the **FTP Task Editor** dialog box to configure the FTP operation that the task performs.</span></span>  
  
 <span data-ttu-id="feb38-104">Per altre informazioni su questa attività, vedere [FTP Task](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="feb38-104">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="feb38-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="feb38-105">Options</span></span>  
 <span data-ttu-id="feb38-106">**IsRemotePathVariable**</span><span class="sxs-lookup"><span data-stu-id="feb38-106">**IsRemotePathVariable**</span></span>  
 <span data-ttu-id="feb38-107">Consente di specificare se il percorso remoto è archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="feb38-107">Indicate whether the remote path is stored in a variable.</span></span> <span data-ttu-id="feb38-108">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="feb38-108">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="feb38-109">valore</span><span class="sxs-lookup"><span data-stu-id="feb38-109">Value</span></span>|<span data-ttu-id="feb38-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="feb38-110">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="feb38-111">**True**</span><span class="sxs-lookup"><span data-stu-id="feb38-111">**True**</span></span>|<span data-ttu-id="feb38-112">Il percorso di destinazione è archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="feb38-112">The destination path is stored in a variable.</span></span> <span data-ttu-id="feb38-113">Selezionando il valore viene visualizzata l'opzione dinamica **RemoteVariable**.</span><span class="sxs-lookup"><span data-stu-id="feb38-113">Selecting the value displays the dynamic option, **RemoteVariable**.</span></span>|  
|<span data-ttu-id="feb38-114">**False**</span><span class="sxs-lookup"><span data-stu-id="feb38-114">**False**</span></span>|<span data-ttu-id="feb38-115">Il percorso di destinazione è specificato in una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="feb38-115">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="feb38-116">Selezionando il valore viene visualizzata l'opzione dinamica **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-116">Selecting the value displays the dynamic option, **RemotePath**.</span></span>|  
  
 <span data-ttu-id="feb38-117">**OverwriteFileAtDestination**</span><span class="sxs-lookup"><span data-stu-id="feb38-117">**OverwriteFileAtDestination**</span></span>  
 <span data-ttu-id="feb38-118">Consente di specificare se è possibile sovrascrivere un file nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="feb38-118">Specify whether a file at the destination can be overwritten.</span></span>  
  
 <span data-ttu-id="feb38-119">**IsLocalPathVariable**</span><span class="sxs-lookup"><span data-stu-id="feb38-119">**IsLocalPathVariable**</span></span>  
 <span data-ttu-id="feb38-120">Consente di specificare se il percorso locale è archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="feb38-120">Indicate whether the local path is stored in a variable.</span></span> <span data-ttu-id="feb38-121">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="feb38-121">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="feb38-122">valore</span><span class="sxs-lookup"><span data-stu-id="feb38-122">Value</span></span>|<span data-ttu-id="feb38-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="feb38-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="feb38-124">**True**</span><span class="sxs-lookup"><span data-stu-id="feb38-124">**True**</span></span>|<span data-ttu-id="feb38-125">Il percorso di destinazione è archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="feb38-125">The destination path is stored in a variable.</span></span> <span data-ttu-id="feb38-126">Selezionando il valore viene visualizzata l'opzione dinamica **LocalVariable**.</span><span class="sxs-lookup"><span data-stu-id="feb38-126">Selecting the value displays the dynamic option, **LocalVariable**.</span></span>|  
|<span data-ttu-id="feb38-127">**False**</span><span class="sxs-lookup"><span data-stu-id="feb38-127">**False**</span></span>|<span data-ttu-id="feb38-128">Il percorso di destinazione è specificato in una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="feb38-128">The destination path is specified in a File connection manager.</span></span> <span data-ttu-id="feb38-129">Selezionando il valore viene visualizzata l'opzione dinamica **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-129">Selecting the value displays the dynamic option, **LocalPath**.</span></span>|  
  
 <span data-ttu-id="feb38-130">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="feb38-130">**Operation**</span></span>  
 <span data-ttu-id="feb38-131">Consente di selezionare l'operazione FTP da eseguire.</span><span class="sxs-lookup"><span data-stu-id="feb38-131">Select the FTP operation to perform.</span></span> <span data-ttu-id="feb38-132">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="feb38-132">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="feb38-133">valore</span><span class="sxs-lookup"><span data-stu-id="feb38-133">Value</span></span>|<span data-ttu-id="feb38-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="feb38-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="feb38-135">**Invia file**</span><span class="sxs-lookup"><span data-stu-id="feb38-135">**Send files**</span></span>|<span data-ttu-id="feb38-136">Consente di inviare i file.</span><span class="sxs-lookup"><span data-stu-id="feb38-136">Send files.</span></span> <span data-ttu-id="feb38-137">Selezionando questo valore vengono visualizzate le opzioni dinamiche **LocalVariable**, **LocalPathRemoteVariable** e **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-137">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="feb38-138">**Ricevi file**</span><span class="sxs-lookup"><span data-stu-id="feb38-138">**Receive files**</span></span>|<span data-ttu-id="feb38-139">Consente di ricevere i file.</span><span class="sxs-lookup"><span data-stu-id="feb38-139">Receive files.</span></span> <span data-ttu-id="feb38-140">Selezionando questo valore vengono visualizzate le opzioni dinamiche **LocalVariable**, **LocalPathRemoteVariable** e **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-140">Selecting this value displays the dynamic options, **LocalVariable**, **LocalPathRemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="feb38-141">**Crea directory locale**</span><span class="sxs-lookup"><span data-stu-id="feb38-141">**Create local directory**</span></span>|<span data-ttu-id="feb38-142">Consente di creare una directory locale.</span><span class="sxs-lookup"><span data-stu-id="feb38-142">Create a local directory.</span></span> <span data-ttu-id="feb38-143">Selezionando questo valore vengono visualizzate le opzioni dinamiche **LocalVariable** e **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-143">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="feb38-144">**Crea directory remota**</span><span class="sxs-lookup"><span data-stu-id="feb38-144">**Create remote directory**</span></span>|<span data-ttu-id="feb38-145">Consente di creare una directory remota.</span><span class="sxs-lookup"><span data-stu-id="feb38-145">Create a remote directory.</span></span> <span data-ttu-id="feb38-146">Selezionando questo valore vengono visualizzate le opzioni dinamiche **RemoteVariable** e **RemotelPath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-146">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotelPath**.</span></span>|  
|<span data-ttu-id="feb38-147">**Rimuovi directory locale**</span><span class="sxs-lookup"><span data-stu-id="feb38-147">**Remove local directory**</span></span>|<span data-ttu-id="feb38-148">Consente di rimuovere una directory locale.</span><span class="sxs-lookup"><span data-stu-id="feb38-148">Removes a local directory.</span></span> <span data-ttu-id="feb38-149">Selezionando questo valore vengono visualizzate le opzioni dinamiche **LocalVariable** e **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-149">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="feb38-150">**Rimuovi directory remota**</span><span class="sxs-lookup"><span data-stu-id="feb38-150">**Remove remote directory**</span></span>|<span data-ttu-id="feb38-151">Consente di rimuovere una directory remota.</span><span class="sxs-lookup"><span data-stu-id="feb38-151">Remove a remote directory.</span></span> <span data-ttu-id="feb38-152">Selezionando questo valore vengono visualizzate le opzioni dinamiche **RemoteVariable** e **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-152">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
|<span data-ttu-id="feb38-153">**Elimina file locali**</span><span class="sxs-lookup"><span data-stu-id="feb38-153">**Delete local files**</span></span>|<span data-ttu-id="feb38-154">Consente di eliminare file locali.</span><span class="sxs-lookup"><span data-stu-id="feb38-154">Delete local files.</span></span> <span data-ttu-id="feb38-155">Selezionando questo valore vengono visualizzate le opzioni dinamiche **LocalVariable** e **LocalPath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-155">Selecting this value displays the dynamic options, **LocalVariable** and **LocalPath**.</span></span>|  
|<span data-ttu-id="feb38-156">**Elimina file remoti**</span><span class="sxs-lookup"><span data-stu-id="feb38-156">**Delete remote files**</span></span>|<span data-ttu-id="feb38-157">Consente di eliminare file remoti.</span><span class="sxs-lookup"><span data-stu-id="feb38-157">Delete remote files.</span></span> <span data-ttu-id="feb38-158">Selezionando questo valore vengono visualizzate le opzioni dinamiche **RemoteVariable** e **RemotePath**.</span><span class="sxs-lookup"><span data-stu-id="feb38-158">Selecting this value displays the dynamic options, **RemoteVariable** and **RemotePath**.</span></span>|  
  
 <span data-ttu-id="feb38-159">**IsTransferASCII**</span><span class="sxs-lookup"><span data-stu-id="feb38-159">**IsTransferASCII**</span></span>  
 <span data-ttu-id="feb38-160">Consente di specificare se i file ricevuti e inviati dal server FTP remoto devono essere trasferiti in modalità ASCII.</span><span class="sxs-lookup"><span data-stu-id="feb38-160">Indicate whether files transferred to and from the remote FTP server should be transferred in ASCII mode.</span></span>  
  
## <a name="isremotepathvariable-dynamic-options"></a><span data-ttu-id="feb38-161">Opzioni dinamiche di IsRemotePathVariable</span><span class="sxs-lookup"><span data-stu-id="feb38-161">IsRemotePathVariable Dynamic Options</span></span>  
  
### <a name="isremotepathvariable--true"></a><span data-ttu-id="feb38-162">IsRemotePathVariable = True</span><span class="sxs-lookup"><span data-stu-id="feb38-162">IsRemotePathVariable = True</span></span>  
 <span data-ttu-id="feb38-163">**RemoteVariable**</span><span class="sxs-lookup"><span data-stu-id="feb38-163">**RemoteVariable**</span></span>  
 <span data-ttu-id="feb38-164">Consente di selezionare una variabile esistente definita dall'utente o di creare una variabile facendo clic su \<**New variable...**>.</span><span class="sxs-lookup"><span data-stu-id="feb38-164">Select an existing user-defined variable, or click \<**New variable...**> to create a user-defined variable.</span></span>  
  
 <span data-ttu-id="feb38-165">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Aggiungere una variabile</span><span class="sxs-lookup"><span data-stu-id="feb38-165">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="isremotepathvariable--false"></a><span data-ttu-id="feb38-166">IsRemotePathVariable = False</span><span class="sxs-lookup"><span data-stu-id="feb38-166">IsRemotePathVariable = False</span></span>  
 <span data-ttu-id="feb38-167">**RemotePath**</span><span class="sxs-lookup"><span data-stu-id="feb38-167">**RemotePath**</span></span>  
 <span data-ttu-id="feb38-168">Consente di selezionare una gestione connessione FTP esistente o di creare una gestione connessione facendo clic su \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="feb38-168">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="feb38-169">**Argomenti correlati:** [Gestione connessione FTP](connection-manager/ftp-connection-manager.md), [Editor gestione connessione FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="feb38-169">**Related Topics:** [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
## <a name="islocalpathvariable-dynamic-options"></a><span data-ttu-id="feb38-170">Opzioni dinamiche di IsLocalPathVariable</span><span class="sxs-lookup"><span data-stu-id="feb38-170">IsLocalPathVariable Dynamic Options</span></span>  
  
### <a name="islocalpathvariable--true"></a><span data-ttu-id="feb38-171">IsLocalPathVariable = True</span><span class="sxs-lookup"><span data-stu-id="feb38-171">IsLocalPathVariable = True</span></span>  
 <span data-ttu-id="feb38-172">**LocalVariable**</span><span class="sxs-lookup"><span data-stu-id="feb38-172">**LocalVariable**</span></span>  
 <span data-ttu-id="feb38-173">Consente di selezionare una variabile esistente definita dall'utente o di creare una variabile facendo clic su \<**New variable...**>.</span><span class="sxs-lookup"><span data-stu-id="feb38-173">Select an existing user-defined variable, or click \<**New variable...**> to create a variable.</span></span>  
  
 <span data-ttu-id="feb38-174">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), Aggiungere una variabile</span><span class="sxs-lookup"><span data-stu-id="feb38-174">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), Add Variable</span></span>  
  
### <a name="islocalpathvariable--false"></a><span data-ttu-id="feb38-175">IsLocalPathVariable = False</span><span class="sxs-lookup"><span data-stu-id="feb38-175">IsLocalPathVariable = False</span></span>  
 <span data-ttu-id="feb38-176">**LocalPath**</span><span class="sxs-lookup"><span data-stu-id="feb38-176">**LocalPath**</span></span>  
 <span data-ttu-id="feb38-177">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="feb38-177">Select an existing File connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
 <span data-ttu-id="feb38-178">**Argomenti correlati:**[Gestione connessione file flat](connection-manager/file-connection-manager.md), [Editor gestione connessione file flat](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="feb38-178">**Related Topics**: [Flat File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feb38-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="feb38-179">See Also</span></span>  
 <span data-ttu-id="feb38-180">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="feb38-180">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="feb38-181">[Editor attività FTP &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="feb38-181">[FTP Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="feb38-182">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="feb38-182">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
