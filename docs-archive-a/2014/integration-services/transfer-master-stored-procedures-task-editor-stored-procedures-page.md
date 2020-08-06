---
title: Editor attività Trasferisci stored procedure master (pagina stored procedure) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.storedprocedures.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: 5fcf171e-cc0b-4c24-8eb5-3a4b4775e64a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f9fad408b54d4ef27d4c5d06b0d352f366ad9c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718456"
---
# <a name="transfer-master-stored-procedures-task-editor-stored-procedures-page"></a><span data-ttu-id="a5571-102">Editor attività Trasferisci stored procedure master (pagina Stored procedure)</span><span class="sxs-lookup"><span data-stu-id="a5571-102">Transfer Master Stored Procedures Task Editor (Stored Procedures Page)</span></span>
  <span data-ttu-id="a5571-103">Usare la pagina **Stored procedure** della finestra di dialogo **Editor attività Trasferisci stored procedure master** per specificare le proprietà per la copia di una o più stored procedure definite dall'utente dal database **master** di un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] a un database **master** di un'altra istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a5571-103">Use the **Stored Procedures** page of the **Transfer Master Stored Procedures Task Editor** dialog box to specify properties for copying one or more user-defined stored procedures from the **master** database in one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance to a **master** database in another instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5571-104">Per altre informazioni su questa attività, vedere [Attività Trasferisci stored procedure master](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="a5571-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5571-105">L'attività consente solo il trasferimento di stored procedure appartenenti a **dbo** da un database **master** del server di origine a un database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="a5571-106">Per poter creare stored procedure nel server di destinazione, gli utenti devono disporre dell'autorizzazione CREATE PROCEDURE nel database **master** del server di destinazione o essere membri del ruolo predefinito del server **sysadmin** nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a5571-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a5571-107">Options</span></span>  
 <span data-ttu-id="a5571-108">**SourceConnection**</span><span class="sxs-lookup"><span data-stu-id="a5571-108">**SourceConnection**</span></span>  
 <span data-ttu-id="a5571-109">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di origine.</span><span class="sxs-lookup"><span data-stu-id="a5571-109">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the source server.</span></span>  
  
 <span data-ttu-id="a5571-110">**DestinationConnection**</span><span class="sxs-lookup"><span data-stu-id="a5571-110">**DestinationConnection**</span></span>  
 <span data-ttu-id="a5571-111">Selezionare una gestione connessione SMO nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova connessione al server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-111">Select a SMO connection manager in the list, or click **\<New connection...>** to create a new connection to the destination server.</span></span>  
  
 <span data-ttu-id="a5571-112">**IfObjectExists**</span><span class="sxs-lookup"><span data-stu-id="a5571-112">**IfObjectExists**</span></span>  
 <span data-ttu-id="a5571-113">Selezionare la modalità con cui l'attività deve gestire le stored procedure definite dall'utente che hanno lo stesso nome di stored procedure già esistenti nel database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-113">Select how the task should handle user-defined stored procedures of the same name that already exist in the **master** database on the destination server.</span></span>  
  
 <span data-ttu-id="a5571-114">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="a5571-114">This property has the options listed in the following table:</span></span>  
  
|<span data-ttu-id="a5571-115">valore</span><span class="sxs-lookup"><span data-stu-id="a5571-115">Value</span></span>|<span data-ttu-id="a5571-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5571-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5571-117">**FailTask**</span><span class="sxs-lookup"><span data-stu-id="a5571-117">**FailTask**</span></span>|<span data-ttu-id="a5571-118">L'attività viene interrotta se nel database **master** del server di destinazione esistono già stored procedure con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="a5571-118">Task fails if stored procedures of the same name already exist in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="a5571-119">**Overwrite**</span><span class="sxs-lookup"><span data-stu-id="a5571-119">**Overwrite**</span></span>|<span data-ttu-id="a5571-120">L'attività sovrascrive le stored procedure con lo stesso nome presenti nel database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-120">Task overwrites stored procedures of the same name in the **master** database on the destination server.</span></span>|  
|<span data-ttu-id="a5571-121">**Skip**</span><span class="sxs-lookup"><span data-stu-id="a5571-121">**Skip**</span></span>|<span data-ttu-id="a5571-122">L'attività ignora le stored procedure con lo stesso nome presenti nel database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-122">Task skips stored procedures of the same name that exist in the **master** database on the destination server.</span></span>|  
  
 <span data-ttu-id="a5571-123">**TransferAllStoredProcedures**</span><span class="sxs-lookup"><span data-stu-id="a5571-123">**TransferAllStoredProcedures**</span></span>  
 <span data-ttu-id="a5571-124">Selezionare un valore per indicare se nel server di destinazione debbano essere copiate tutte le stored procedure definite dall'utente nel database **master** del server di origine.</span><span class="sxs-lookup"><span data-stu-id="a5571-124">Select whether all user-defined stored procedures in the **master** database on the source server should be copied to the destination server.</span></span>  
  
|<span data-ttu-id="a5571-125">valore</span><span class="sxs-lookup"><span data-stu-id="a5571-125">Value</span></span>|<span data-ttu-id="a5571-126">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a5571-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a5571-127">**True**</span><span class="sxs-lookup"><span data-stu-id="a5571-127">**True**</span></span>|<span data-ttu-id="a5571-128">Copia tutte le stored procedure definite dall'utente nel database **master** .</span><span class="sxs-lookup"><span data-stu-id="a5571-128">Copy all user-defined stored procedures in the **master** database.</span></span>|  
|<span data-ttu-id="a5571-129">**False**</span><span class="sxs-lookup"><span data-stu-id="a5571-129">**False**</span></span>|<span data-ttu-id="a5571-130">Copia solo le stored procedure specificate.</span><span class="sxs-lookup"><span data-stu-id="a5571-130">Copy only the specified stored procedures.</span></span>|  
  
 <span data-ttu-id="a5571-131">**StoredProceduresList**</span><span class="sxs-lookup"><span data-stu-id="a5571-131">**StoredProceduresList**</span></span>  
 <span data-ttu-id="a5571-132">Selezionare le stored procedure definite dall'utente nel database **master** del server di origine da copiare nel database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a5571-132">Select which user-defined stored procedures in the **master** database on the source server should be copied to the destination **master** database.</span></span> <span data-ttu-id="a5571-133">Questa opzione è disponibile solo quando la proprietà **TransferAllStoredProcedures** è impostata su **False**.</span><span class="sxs-lookup"><span data-stu-id="a5571-133">This option is only available when **TransferAllStoredProcedures** is set to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5571-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5571-134">See Also</span></span>  
 <span data-ttu-id="a5571-135">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a5571-135">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a5571-136">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="a5571-136">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="a5571-137">[Editor attività Trasferisci stored procedure master &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="a5571-137">[Transfer Master Stored Procedures Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="a5571-138">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="a5571-138">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="a5571-139">Gestione connessione SMO</span><span class="sxs-lookup"><span data-stu-id="a5571-139">SMO Connection Manager</span></span>](connection-manager/smo-connection-manager.md)  
  
  
