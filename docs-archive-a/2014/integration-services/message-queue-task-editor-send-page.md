---
title: Editor attività Message Queue (pagina invio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727035"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="2d553-102">Editor attività Message Queue (pagina Invio)</span><span class="sxs-lookup"><span data-stu-id="2d553-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="2d553-103">Usare la pagina **Invio** della finestra di dialogo **Editor attività Message Queue** per configurare un'attività Message Queue per l'invio di messaggi da un pacchetto di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d553-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="2d553-104">Per ulteriori informazioni su questa attività, vedere [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="2d553-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2d553-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2d553-105">Options</span></span>  
 <span data-ttu-id="2d553-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="2d553-106">**UseEncryption**</span></span>  
 <span data-ttu-id="2d553-107">Consente di indicare se crittografare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="2d553-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="2d553-108">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="2d553-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="2d553-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="2d553-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="2d553-110">Se si sceglie di utilizzare la crittografia, consente di specificare il nome dell'algoritmo di crittografia da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2d553-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="2d553-111">L'attività Message Queue può utilizzare gli algoritmi RC2 e RC4.</span><span class="sxs-lookup"><span data-stu-id="2d553-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="2d553-112">L'impostazione predefinita è **RC2**.</span><span class="sxs-lookup"><span data-stu-id="2d553-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d553-113">L'algoritmo RC4 è supportato solo per motivi di compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2d553-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="2d553-114">È possibile crittografare il nuovo materiale usando RC4 o RC4_128 solo quando il livello di compatibilità del database è 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="2d553-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="2d553-115">(Non consigliato.) Usare un algoritmo più recente, ad esempio uno degli algoritmi AES.</span><span class="sxs-lookup"><span data-stu-id="2d553-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="2d553-116">Nella versione corrente di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]il materiale crittografato utilizzando RC4 o RC4_128 può essere decrittografato in qualsiasi livello di compatibilità.</span><span class="sxs-lookup"><span data-stu-id="2d553-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d553-117">Questi algoritmi di crittografia sono quelli supportati dalla tecnologia Microsoft Message Queuing (nota anche come MSMQ).</span><span class="sxs-lookup"><span data-stu-id="2d553-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="2d553-118">Entrambi gli algoritmi di crittografia sono ormai considerati vulnerabili rispetto ad altri più recenti che tuttavia non sono ancora supportati da MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2d553-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="2d553-119">È pertanto consigliabile valutare con attenzione le esigenze di crittografia ai fini dell'invio di messaggi tramite l'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="2d553-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="2d553-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="2d553-120">**MessageType**</span></span>  
 <span data-ttu-id="2d553-121">Consente di selezionare il tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="2d553-121">Select the message type.</span></span> <span data-ttu-id="2d553-122">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2d553-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="2d553-123">valore</span><span class="sxs-lookup"><span data-stu-id="2d553-123">Value</span></span>|<span data-ttu-id="2d553-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d553-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2d553-125">**Messaggio file di dati**</span><span class="sxs-lookup"><span data-stu-id="2d553-125">**Data file message**</span></span>|<span data-ttu-id="2d553-126">Il messaggio viene archiviato in un file.</span><span class="sxs-lookup"><span data-stu-id="2d553-126">The message is stored in a file.</span></span> <span data-ttu-id="2d553-127">La selezione del valore determina la visualizzazione dell'opzione dinamica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="2d553-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="2d553-128">**Messaggio variabili**</span><span class="sxs-lookup"><span data-stu-id="2d553-128">**Variable message**</span></span>|<span data-ttu-id="2d553-129">Il messaggio viene archiviato in una variabile.</span><span class="sxs-lookup"><span data-stu-id="2d553-129">The message is stored in a variable.</span></span> <span data-ttu-id="2d553-130">La selezione del valore determina la visualizzazione dell'opzione dinamica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="2d553-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="2d553-131">**Messaggio stringa**</span><span class="sxs-lookup"><span data-stu-id="2d553-131">**String message**</span></span>|<span data-ttu-id="2d553-132">Il messaggio viene archiviato nell'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="2d553-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="2d553-133">La selezione del valore determina la visualizzazione dell'opzione dinamica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="2d553-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="2d553-134">Opzioni dinamiche di MessageType</span><span class="sxs-lookup"><span data-stu-id="2d553-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="2d553-135">MessageType = Messaggio file di dati</span><span class="sxs-lookup"><span data-stu-id="2d553-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="2d553-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="2d553-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="2d553-137">Digitare il percorso del file di dati o fare clic sui puntini di sospensione **(...)** e quindi individuare il file.</span><span class="sxs-lookup"><span data-stu-id="2d553-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="2d553-138">MessageType = Messaggio variabili</span><span class="sxs-lookup"><span data-stu-id="2d553-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="2d553-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="2d553-139">**VariableMessage**</span></span>  
 <span data-ttu-id="2d553-140">Digitare i nomi delle variabili o fare clic sui puntini di sospensione **(...)** e quindi selezionare le variabili.</span><span class="sxs-lookup"><span data-stu-id="2d553-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="2d553-141">Le variabili sono separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="2d553-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="2d553-142">**Argomenti correlati:** Seleziona variabili</span><span class="sxs-lookup"><span data-stu-id="2d553-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="2d553-143">MessageType = Messaggio stringa</span><span class="sxs-lookup"><span data-stu-id="2d553-143">MessageType = String message</span></span>  
 <span data-ttu-id="2d553-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="2d553-144">**StringMessage**</span></span>  
 <span data-ttu-id="2d553-145">Digitare il messaggio stringa o fare clic sui puntini di sospensione **(...)** e quindi digitare il messaggio nella finestra di dialogo **Immettere il messaggio stringa**.</span><span class="sxs-lookup"><span data-stu-id="2d553-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d553-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d553-146">See Also</span></span>  
 <span data-ttu-id="2d553-147">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2d553-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2d553-148">[Editor attività Message Queue &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2d553-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2d553-149">[Editor attività Message Queue &#40;pagina ricezione&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="2d553-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="2d553-150">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="2d553-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
