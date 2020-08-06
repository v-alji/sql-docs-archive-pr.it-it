---
title: Editor gestione connessione HTTP (pagina proxy) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.proxy.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: e831a830-49a3-49c5-8a31-9731fc4fd12e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f8269dbbeb226ffa3f56c226e1a416d99c1e3f13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624834"
---
# <a name="http-connection-manager-editor-proxy-page"></a><span data-ttu-id="913c1-102">Editor gestione connessione HTTP (pagina Proxy)</span><span class="sxs-lookup"><span data-stu-id="913c1-102">HTTP Connection Manager Editor (Proxy Page)</span></span>
  <span data-ttu-id="913c1-103">La scheda **Proxy** della finestra di dialogo **Editor gestione connessione HTTP** consente di configurare Gestione connessione HTTP in modo che utilizzi un server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-103">Use the **Proxy** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager to use a proxy server.</span></span> <span data-ttu-id="913c1-104">Una connessione HTTP consente a un pacchetto di accedere al server Web utilizzando il protocollo HTTP per l'invio o la ricezione di file.</span><span class="sxs-lookup"><span data-stu-id="913c1-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span>  
  
 <span data-ttu-id="913c1-105">Per ulteriori informazioni sulla gestione connessione HTTP, vedere [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="913c1-105">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="913c1-106">Per ulteriori informazioni su uno scenario di utilizzo comune della gestione connessione HTTP, vedere [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="913c1-106">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="913c1-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="913c1-107">Options</span></span>  
 <span data-ttu-id="913c1-108">**Usa proxy**</span><span class="sxs-lookup"><span data-stu-id="913c1-108">**Use proxy**</span></span>  
 <span data-ttu-id="913c1-109">Consente di specificare se per la gestione connessione HTTP è necessario connettersi tramite un server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-109">Specify whether you want the HTTP Connection Manager to connect through a proxy server.</span></span>  
  
 <span data-ttu-id="913c1-110">**URL proxy**</span><span class="sxs-lookup"><span data-stu-id="913c1-110">**Proxy URL**</span></span>  
 <span data-ttu-id="913c1-111">Consente di digitare l'URL del server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-111">Type the URL for the proxy server.</span></span>  
  
 <span data-ttu-id="913c1-112">**Ignora proxy in locale**</span><span class="sxs-lookup"><span data-stu-id="913c1-112">**Bypass proxy on local**</span></span>  
 <span data-ttu-id="913c1-113">Consente di specificare se per la gestione connessione HTTP è necessario ignorare il server proxy per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="913c1-113">Specify whether you want the HTTP Connection Manager to bypass the proxy server for local addresses.</span></span>  
  
 <span data-ttu-id="913c1-114">**Usa credenziali**</span><span class="sxs-lookup"><span data-stu-id="913c1-114">**Use credentials**</span></span>  
 <span data-ttu-id="913c1-115">Consente di specificare se per la gestione connessione HTTP è necessario utilizzare le credenziali di sicurezza per il server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-115">Specify whether you want the HTTP Connection Manager to use security credentials for the proxy server.</span></span>  
  
 <span data-ttu-id="913c1-116">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="913c1-116">**User name**</span></span>  
 <span data-ttu-id="913c1-117">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="913c1-117">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="913c1-118">**Password**</span><span class="sxs-lookup"><span data-stu-id="913c1-118">**Password**</span></span>  
 <span data-ttu-id="913c1-119">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="913c1-119">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="913c1-120">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="913c1-120">**Domain**</span></span>  
 <span data-ttu-id="913c1-121">Se per la gestione connessione HTTP è stato impostato l'utilizzo di credenziali, è necessario specificare nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="913c1-121">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="913c1-122">**Elenco proxy da ignorare**</span><span class="sxs-lookup"><span data-stu-id="913c1-122">**Proxy bypass list**</span></span>  
 <span data-ttu-id="913c1-123">Elenco degli indirizzi per i quali si desidera ignorare il server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-123">The list of addresses for which  you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="913c1-124">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="913c1-124">**Add**</span></span>  
 <span data-ttu-id="913c1-125">Consente di digitare un indirizzo per il quale si desidera ignorare il server proxy.</span><span class="sxs-lookup"><span data-stu-id="913c1-125">Type an address for which you want to bypass the proxy server.</span></span>  
  
 <span data-ttu-id="913c1-126">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="913c1-126">**Remove**</span></span>  
 <span data-ttu-id="913c1-127">Consente di selezionare un indirizzo e quindi di rimuoverlo facendo clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="913c1-127">Select an address, and then remove it by clicking **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913c1-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="913c1-128">See Also</span></span>  
 <span data-ttu-id="913c1-129">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="913c1-129">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="913c1-130">Editor gestione connessione HTTP &#40;pagina Server&#41;</span><span class="sxs-lookup"><span data-stu-id="913c1-130">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-server-page.md)  
  
  
