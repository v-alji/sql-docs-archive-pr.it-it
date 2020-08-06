---
title: Editor gestione connessione HTTP (pagina Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624829"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="d5323-102">Editor gestione connessione HTTP (pagina Server)</span><span class="sxs-lookup"><span data-stu-id="d5323-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="d5323-103">La scheda **Server** della finestra di dialogo **Editor gestione connessione HTTP** consente di configurare la gestione connessione HTTP specificando proprietà quali l'URL e le credenziali di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d5323-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="d5323-104">Una connessione HTTP consente a un pacchetto di accedere al server Web utilizzando il protocollo HTTP per l'invio o la ricezione di file.</span><span class="sxs-lookup"><span data-stu-id="d5323-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="d5323-105">Dopo aver configurato la gestione connessione HTTP sarà inoltre possibile verificare la connessione.</span><span class="sxs-lookup"><span data-stu-id="d5323-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d5323-106">La gestione connessione HTTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="d5323-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="d5323-107">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d5323-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="d5323-108">Per ulteriori informazioni sulla gestione connessione HTTP, vedere [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d5323-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="d5323-109">Per ulteriori informazioni su uno scenario di utilizzo comune della gestione connessione HTTP, vedere [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="d5323-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d5323-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d5323-110">Options</span></span>  
 <span data-ttu-id="d5323-111">**URL del server**</span><span class="sxs-lookup"><span data-stu-id="d5323-111">**Server URL**</span></span>  
 <span data-ttu-id="d5323-112">Digitare l'URL per il server.</span><span class="sxs-lookup"><span data-stu-id="d5323-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="d5323-113">Se si intende utilizzare il pulsante **Scarica WSDL** nella pagina **Generale** di **Editor attività Servizio Web** per scaricare un file WSDL, digitare l'URL del file WSDL.</span><span class="sxs-lookup"><span data-stu-id="d5323-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="d5323-114">L'URL termina con "?wsdl".</span><span class="sxs-lookup"><span data-stu-id="d5323-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="d5323-115">**Usa credenziali**</span><span class="sxs-lookup"><span data-stu-id="d5323-115">**Use credentials**</span></span>  
 <span data-ttu-id="d5323-116">Consente di specificare se si desidera che per la gestione connessione HTTP vengano utilizzate le credenziali di sicurezza dell'utente per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d5323-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="d5323-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d5323-117">**User name**</span></span>  
 <span data-ttu-id="d5323-118">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="d5323-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d5323-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="d5323-119">**Password**</span></span>  
 <span data-ttu-id="d5323-120">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="d5323-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d5323-121">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="d5323-121">**Domain**</span></span>  
 <span data-ttu-id="d5323-122">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="d5323-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="d5323-123">**Usa certificato client**</span><span class="sxs-lookup"><span data-stu-id="d5323-123">**Use client certificate**</span></span>  
 <span data-ttu-id="d5323-124">Consente di specificare se si desidera che per la gestione connessione HTTP venga utilizzato un certificato client per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d5323-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="d5323-125">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="d5323-125">**Certificate**</span></span>  
 <span data-ttu-id="d5323-126">Consente di selezionare un certificato nell'elenco usando la finestra di dialogo **Seleziona certificato** .</span><span class="sxs-lookup"><span data-stu-id="d5323-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="d5323-127">Nella casella di testo viene visualizzato il nome associato al certificato.</span><span class="sxs-lookup"><span data-stu-id="d5323-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="d5323-128">**Timeout (in secondi)**</span><span class="sxs-lookup"><span data-stu-id="d5323-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="d5323-129">Consente di fornire un valore di timeout per la connessione al server Web.</span><span class="sxs-lookup"><span data-stu-id="d5323-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="d5323-130">Il valore predefinito di questa proprietà è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="d5323-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="d5323-131">**Dimensioni blocco (in KB)**</span><span class="sxs-lookup"><span data-stu-id="d5323-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="d5323-132">Consente di specificare le dimensioni del blocco per la scrittura dei dati.</span><span class="sxs-lookup"><span data-stu-id="d5323-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="d5323-133">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="d5323-133">**Test Connection**</span></span>  
 <span data-ttu-id="d5323-134">Dopo aver configurato la gestione connessione HTTP, fare clic su **Test connessione**per assicurarsi che la connessione sia operativa.</span><span class="sxs-lookup"><span data-stu-id="d5323-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5323-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5323-135">See Also</span></span>  
 <span data-ttu-id="d5323-136">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d5323-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="d5323-137">Editor gestione connessione HTTP &#40;pagina Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="d5323-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
