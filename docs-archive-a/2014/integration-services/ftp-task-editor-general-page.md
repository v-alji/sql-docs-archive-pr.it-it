---
title: Editor attività FTP (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftptask.general.f1
helpviewer_keywords:
- File Transfer Protocol Task Editor
ms.assetid: 28b46fdd-b04a-4f97-a99f-883f5735a6d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0cb4ffe2fa44e76890f6b70912f84dbcaa8f2cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626147"
---
# <a name="ftp-task-editor-general-page"></a><span data-ttu-id="ef0d0-102">Editor attività FTP (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="ef0d0-102">FTP Task Editor (General Page)</span></span>
  <span data-ttu-id="ef0d0-103">Utilizzare la pagina **Generale** della finestra di dialogo **Editor attività FTP** per specificare la gestione connessione FTP tramite cui viene stabilita la connessione al server FTP con cui comunica l'attività.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-103">Use the **General** page of the **FTP Task Editor** dialog box to specify the FTP connection manager that connects to the FTP server that the task communicates with.</span></span> <span data-ttu-id="ef0d0-104">È inoltre possibile specificare un nome e una descrizione per l'attività FTP.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-104">You can also name and describe the FTP task.</span></span>  
  
 <span data-ttu-id="ef0d0-105">Per altre informazioni su questa attività, vedere [FTP Task](control-flow/ftp-task.md).</span><span class="sxs-lookup"><span data-stu-id="ef0d0-105">To learn about this task, see [FTP Task](control-flow/ftp-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ef0d0-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ef0d0-106">Options</span></span>  
 <span data-ttu-id="ef0d0-107">**FtpConnection**</span><span class="sxs-lookup"><span data-stu-id="ef0d0-107">**FtpConnection**</span></span>  
 <span data-ttu-id="ef0d0-108">Consente di selezionare una gestione connessione FTP esistente o di creare una gestione connessione facendo clic su \<**New connection...**>.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-108">Select an existing FTP connection manager, or click \<**New connection...**> to create a connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ef0d0-109">La gestione connessione FTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-109">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="ef0d0-110">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-110">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="ef0d0-111">**Argomenti correlati**: [Gestione connessione FTP](connection-manager/ftp-connection-manager.md), [Editor gestione connessione FTP](../../2014/integration-services/ftp-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="ef0d0-111">**Related Topics**: [FTP Connection Manager](connection-manager/ftp-connection-manager.md), [FTP Connection Manager Editor](../../2014/integration-services/ftp-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="ef0d0-112">**StopOnFailure**</span><span class="sxs-lookup"><span data-stu-id="ef0d0-112">**StopOnFailure**</span></span>  
 <span data-ttu-id="ef0d0-113">Consente di specificare il termine dell'attività FTP in caso di esito negativo di un'operazione FTP.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-113">Indicate whether the FTP task terminates if an FTP operation fails.</span></span>  
  
 <span data-ttu-id="ef0d0-114">**Nome**</span><span class="sxs-lookup"><span data-stu-id="ef0d0-114">**Name**</span></span>  
 <span data-ttu-id="ef0d0-115">Consente di specificare un nome univoco per l'attività FTP.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-115">Provide a unique name for the FTP task.</span></span> <span data-ttu-id="ef0d0-116">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-116">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef0d0-117">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-117">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="ef0d0-118">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ef0d0-118">**Description**</span></span>  
 <span data-ttu-id="ef0d0-119">Consente di digitare una descrizione dell'attività FTP.</span><span class="sxs-lookup"><span data-stu-id="ef0d0-119">Type a description of the FTP task.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0d0-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef0d0-120">See Also</span></span>  
 <span data-ttu-id="ef0d0-121">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ef0d0-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ef0d0-122">[Editor attività FTP &#40;pagina trasferimento file&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span><span class="sxs-lookup"><span data-stu-id="ef0d0-122">[FTP Task Editor &#40;File Transfer Page&#41;](../../2014/integration-services/ftp-task-editor-file-transfer-page.md) </span></span>  
 [<span data-ttu-id="ef0d0-123">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="ef0d0-123">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
