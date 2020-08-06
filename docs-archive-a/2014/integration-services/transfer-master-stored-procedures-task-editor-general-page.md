---
title: Editor attività Trasferisci stored procedure master (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.transferstoredprocedurestask.general.f1
helpviewer_keywords:
- Transfer Stored Procedures Task Editor
ms.assetid: fa1abd4c-e2be-427f-be53-860e49c97227
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8a25a5c9c6ed3802e21ac522e94163ce5fb9e8c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718462"
---
# <a name="transfer-master-stored-procedures-task-editor-general-page"></a><span data-ttu-id="6276c-102">Editor attività Trasferisci stored procedure master (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="6276c-102">Transfer Master Stored Procedures Task Editor (General Page)</span></span>
  <span data-ttu-id="6276c-103">Usare la pagina **Generale** della finestra di dialogo **Editor attività Trasferisci stored procedure master** per assegnare un nome e una descrizione all'attività Trasferisci stored procedure master.</span><span class="sxs-lookup"><span data-stu-id="6276c-103">Use the **General** page of the **Transfer Master Stored Procedures Task Editor** dialog box to name and describe the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="6276c-104">Per altre informazioni su questa attività, vedere [Attività Trasferisci stored procedure master](control-flow/transfer-master-stored-procedures-task.md).</span><span class="sxs-lookup"><span data-stu-id="6276c-104">For more information about this task, see [Transfer Master Stored Procedures Task](control-flow/transfer-master-stored-procedures-task.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6276c-105">L'attività consente solo il trasferimento di stored procedure appartenenti a **dbo** da un database **master** del server di origine a un database **master** del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6276c-105">This task transfers only user-defined stored procedures owned by **dbo** from a **master** database on the source server to a **master** database on the destination server.</span></span> <span data-ttu-id="6276c-106">Per poter creare stored procedure nel server di destinazione, gli utenti devono disporre dell'autorizzazione CREATE PROCEDURE nel database **master** del server di destinazione o essere membri del ruolo predefinito del server **sysadmin** nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="6276c-106">Users must be granted the CREATE PROCEDURE permission in the **master** database on the destination server or be members of the **sysadmin** fixed server role on the destination server to create stored procedures there.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6276c-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="6276c-107">Options</span></span>  
 <span data-ttu-id="6276c-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6276c-108">**Name**</span></span>  
 <span data-ttu-id="6276c-109">Consente di digitare un nome univoco per l'attività Trasferisci stored procedure master.</span><span class="sxs-lookup"><span data-stu-id="6276c-109">Type a unique name for the Transfer Master Stored Procedures task.</span></span> <span data-ttu-id="6276c-110">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="6276c-110">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6276c-111">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6276c-111">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="6276c-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6276c-112">**Description**</span></span>  
 <span data-ttu-id="6276c-113">Consente di digitare una descrizione dell'attività Trasferisci stored procedure master.</span><span class="sxs-lookup"><span data-stu-id="6276c-113">Type a description of the Transfer Master Stored Procedures task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6276c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6276c-114">See Also</span></span>  
 <span data-ttu-id="6276c-115">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="6276c-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="6276c-116">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="6276c-116">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="6276c-117">[Editor attività Trasferisci stored procedure master &#40;pagina stored procedure&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span><span class="sxs-lookup"><span data-stu-id="6276c-117">[Transfer Master Stored Procedures Task Editor &#40;Stored Procedures Page&#41;](../../2014/integration-services/transfer-master-stored-procedures-task-editor-stored-procedures-page.md) </span></span>  
 [<span data-ttu-id="6276c-118">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="6276c-118">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
