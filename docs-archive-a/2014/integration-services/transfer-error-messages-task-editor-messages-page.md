---
title: Editor attività Trasferisci messaggi di errore (pagina messaggi) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transfererrormessagestask.errormessages.F1
helpviewer_keywords:
- Transfer Error Messages Task Editor
ms.assetid: cb2226a0-3037-4fdf-966f-81eabc0da9cf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0d626f01e05a30777810b26880da5aedc3e7ad3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638464"
---
# <a name="transfer-error-messages-task-editor-messages-page"></a><span data-ttu-id="4c0bc-102">Editor attività Trasferisci messaggi di errore (pagina Messaggi)</span><span class="sxs-lookup"><span data-stu-id="4c0bc-102">Transfer Error Messages Task Editor (Messages Page)</span></span>
  <span data-ttu-id="4c0bc-103">Usare la pagina **Messaggi** della finestra di dialogo **Editor attività Trasferisci messaggi di errore** per specificare le proprietà relative alla copia di uno o più messaggi di errore definiti dall'utente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tra due istanze di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4c0bc-103">Use the **Messages** page of the **Transfer Error Messages Task Editor** dialog box to specify properties for copying one or more [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] user-defined error messages from one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to another.</span></span> <span data-ttu-id="4c0bc-104">Per ulteriori informazioni su questa attività, vedere [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span><span class="sxs-lookup"><span data-stu-id="4c0bc-104">For more information about this task, see [Transfer Error Messages Task](control-flow/transfer-error-messages-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c0bc-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4c0bc-105">Options</span></span>  
 <span data-ttu-id="4c0bc-106">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-106">**SourceConnection**</span></span>  
 <span data-ttu-id="4c0bc-107">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-107">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="4c0bc-108">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-108">**DestinationConnection**</span></span>  
 <span data-ttu-id="4c0bc-109">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="4c0bc-110">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-110">**IfObjectExists**</span></span>  
 <span data-ttu-id="4c0bc-111">Indicare se l'attività deve sovrascrivere i messaggi di errore definiti dall'utente esistenti, ignorare i messaggi esistenti oppure interrompersi in caso nel server di destinazione esistano già messaggi di errore con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-111">Select whether the task should overwrite existing user-defined error messages, skip existing messages, or fail if error messages of the same name already exist on the destination server.</span></span>  
  
 <span data-ttu-id="4c0bc-112">**TransferAllErrorMessages**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-112">**TransferAllErrorMessages**</span></span>  
 <span data-ttu-id="4c0bc-113">Indicare se l'attività deve copiare dal server di origine al server di destinazione tutti i messaggi di errore definiti dall'utente o solo quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-113">Select whether the task should copy all or only the specified user-defined messages from the source server to the destination server.</span></span>  
  
 <span data-ttu-id="4c0bc-114">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="4c0bc-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="4c0bc-115">valore</span><span class="sxs-lookup"><span data-stu-id="4c0bc-115">Value</span></span>|<span data-ttu-id="4c0bc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c0bc-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4c0bc-117">**True**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-117">**True**</span></span>|<span data-ttu-id="4c0bc-118">Copia tutti i messaggi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-118">Copy all user-defined messages.</span></span>|  
|<span data-ttu-id="4c0bc-119">**False**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-119">**False**</span></span>|<span data-ttu-id="4c0bc-120">Copia solo i messaggi definiti dall'utente specificati.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-120">Copy only the specified user-defined messages.</span></span>|  
  
 <span data-ttu-id="4c0bc-121">**ErrorMessagesList**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-121">**ErrorMessagesList**</span></span>  
 <span data-ttu-id="4c0bc-122">Fare clic sul pulsante sfoglia **(...)** per selezionare i messaggi di errore da copiare.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-122">Click the browse button **(...)** to select the error messages to copy.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c0bc-123">È necessario specificare la proprietà **SourceConnection** prima di poter selezionare i messaggi di errore di cui eseguire la copia.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-123">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
 <span data-ttu-id="4c0bc-124">**ErrorMessageLanguagesList**</span><span class="sxs-lookup"><span data-stu-id="4c0bc-124">**ErrorMessageLanguagesList**</span></span>  
 <span data-ttu-id="4c0bc-125">Fare clic sul pulsante sfoglia **(...)** per selezionare le lingue per cui copiare i messaggi di errore definiti dall'utente nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-125">Click the browse button **(...)** to select the languages for which to copy user-defined error messages to the destination server.</span></span> <span data-ttu-id="4c0bc-126">Per poter trasferire versioni del messaggio in altre lingue nel server di destinazione, è necessario che in tale server esista una versione us_english (tabella codici 1033) del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-126">A us_english (code page 1033) version of the message must exist on the destination server before you can transfer other language versions of the message to that server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c0bc-127">È necessario specificare la proprietà **SourceConnection** prima di poter selezionare i messaggi di errore di cui eseguire la copia.</span><span class="sxs-lookup"><span data-stu-id="4c0bc-127">You must specify the **SourceConnection** before you can select error messages to copy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c0bc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c0bc-128">See Also</span></span>  
 <span data-ttu-id="4c0bc-129">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4c0bc-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="4c0bc-130">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="4c0bc-130">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="4c0bc-131">[Editor attività Trasferisci messaggi di errore &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4c0bc-131">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="4c0bc-132">[Gestione connessione SMO](connection-manager/smo-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="4c0bc-132">[SMO Connection Manager](connection-manager/smo-connection-manager.md) </span></span>  
 <span data-ttu-id="4c0bc-133">[Editor attività Trasferisci messaggi di errore &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="4c0bc-133">[Transfer Error Messages Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="4c0bc-134">Gestione connessione SMO</span><span class="sxs-lookup"><span data-stu-id="4c0bc-134">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
