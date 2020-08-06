---
title: Editor gestione connessione FTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727047"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="d5271-102">Editor gestione connessione FTP</span><span class="sxs-lookup"><span data-stu-id="d5271-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="d5271-103">Usare la finestra di dialogo **Editor gestione connessione FTP** per specificare le proprietà per la connessione a un server FTP.</span><span class="sxs-lookup"><span data-stu-id="d5271-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5271-104">La gestione connessione FTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d5271-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="d5271-105">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5271-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="d5271-106">Per altre informazioni sulla gestione connessione FTP, vedere [Gestione connessione FTP](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d5271-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5271-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d5271-107">Options</span></span>  
 <span data-ttu-id="d5271-108">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="d5271-108">**Server name**</span></span>  
 <span data-ttu-id="d5271-109">Consente di specificare il nome del server FTP.</span><span class="sxs-lookup"><span data-stu-id="d5271-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="d5271-110">**Porta server**</span><span class="sxs-lookup"><span data-stu-id="d5271-110">**Server port**</span></span>  
 <span data-ttu-id="d5271-111">Consente di specificare il numero di porta del server FTP da utilizzare per la connessione.</span><span class="sxs-lookup"><span data-stu-id="d5271-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="d5271-112">Il valore predefinito di questa proprietà è **21**.</span><span class="sxs-lookup"><span data-stu-id="d5271-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="d5271-113">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d5271-113">**User name**</span></span>  
 <span data-ttu-id="d5271-114">Consente di specificare un nome utente per l'accesso al server FTP.</span><span class="sxs-lookup"><span data-stu-id="d5271-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="d5271-115">Il valore predefinito di questa proprietà è **anonymous**.</span><span class="sxs-lookup"><span data-stu-id="d5271-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="d5271-116">**Password**</span><span class="sxs-lookup"><span data-stu-id="d5271-116">**Password**</span></span>  
 <span data-ttu-id="d5271-117">Consente di specificare una password per l'accesso al server FTP.</span><span class="sxs-lookup"><span data-stu-id="d5271-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="d5271-118">**Timeout (in secondi)**</span><span class="sxs-lookup"><span data-stu-id="d5271-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="d5271-119">Consente di specificare il numero di secondi necessari per l'attività prima del timeout. Il valore **0** indica un periodo di tempo infinito.</span><span class="sxs-lookup"><span data-stu-id="d5271-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="d5271-120">Il valore predefinito di questa proprietà è **60**.</span><span class="sxs-lookup"><span data-stu-id="d5271-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="d5271-121">**Usa modalità passiva**</span><span class="sxs-lookup"><span data-stu-id="d5271-121">**Use passive mode**</span></span>  
 <span data-ttu-id="d5271-122">Consente di specificare se la connessione viene iniziata dal server o dal client.</span><span class="sxs-lookup"><span data-stu-id="d5271-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="d5271-123">Il server inizia la connessione in modalità attiva, mentre il client attiva la connessione in modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="d5271-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="d5271-124">Il valore predefinito di questa proprietà è **active mode**.</span><span class="sxs-lookup"><span data-stu-id="d5271-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="d5271-125">**Tentativi**</span><span class="sxs-lookup"><span data-stu-id="d5271-125">**Retries**</span></span>  
 <span data-ttu-id="d5271-126">Consente di specificare il numeri di tentativi eseguiti dall'attività per stabilire la connessione.</span><span class="sxs-lookup"><span data-stu-id="d5271-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="d5271-127">Il valore **0** indica un numero di tentativi illimitato.</span><span class="sxs-lookup"><span data-stu-id="d5271-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="d5271-128">**Dimensioni blocco (in KB)**</span><span class="sxs-lookup"><span data-stu-id="d5271-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="d5271-129">Consente di specificare le dimensioni del blocco in KB per la trasmissione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d5271-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="d5271-130">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="d5271-130">**Test Connection**</span></span>  
 <span data-ttu-id="d5271-131">Dopo aver configurato la gestione connessione FTP, fare clic su **Test connessione**per assicurarsi che la connessione sia funzionante.</span><span class="sxs-lookup"><span data-stu-id="d5271-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5271-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5271-132">See Also</span></span>  
 [<span data-ttu-id="d5271-133">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="d5271-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
