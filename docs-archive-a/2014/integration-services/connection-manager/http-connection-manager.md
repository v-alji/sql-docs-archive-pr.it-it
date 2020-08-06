---
title: Gestione connessione HTTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- HTTP connection manager
- Web site connections [Integration Services]
- connection managers [Integration Services], HTTP
- Web server connections [Integration Services]
- connections [Integration Services], HTTP
ms.assetid: 26b2b3e1-d02c-46ca-8d31-7aef2bbc3c53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10c9f0778faa25aff8db4ad54ecaa8d3ccc5b359
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724028"
---
# <a name="http-connection-manager"></a><span data-ttu-id="1b0a4-102">gestione connessione HTTP</span><span class="sxs-lookup"><span data-stu-id="1b0a4-102">HTTP Connection Manager</span></span>
  <span data-ttu-id="1b0a4-103">Una connessione HTTP consente a un pacchetto di accedere al server Web utilizzando il protocollo HTTP per l'invio o la ricezione di file.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-103">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="1b0a4-104">Questa gestione connessione viene usata dall'attività Servizio Web inclusa in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b0a4-104">The Web Service task that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager.</span></span>  
  
 <span data-ttu-id="1b0a4-105">Quando si aggiunge una gestione connessione HTTP a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione HTTP, imposta le proprietà della gestione connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-105">When you add an HTTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an HTTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="1b0a4-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `HTTP.`</span><span class="sxs-lookup"><span data-stu-id="1b0a4-106">The `ConnectionManagerType` property of the connection manager is set to `HTTP.`</span></span>  
  
 <span data-ttu-id="1b0a4-107">Per configurare la gestione connessione HTTP, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="1b0a4-107">You can configure the HTTP connection manager the following ways:</span></span>  
  
-   <span data-ttu-id="1b0a4-108">Utilizzo di credenziali.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-108">Use credentials.</span></span> <span data-ttu-id="1b0a4-109">Se la gestione connessione utilizza credenziali, le sue proprietà includeranno nome utente, password e dominio.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-109">If the connection manager uses credentials, its properties include the user name, password, and domain.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="1b0a4-110">La gestione connessione HTTP supporta solo l'autenticazione anonima e l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-110">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="1b0a4-111">Non supporta l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-111">It does not support Windows Authentication.</span></span>  
  
-   <span data-ttu-id="1b0a4-112">Utilizzo di un certificato client.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-112">Use a client certificate.</span></span> <span data-ttu-id="1b0a4-113">Se la gestione connessione utilizza un certificato client, le sue proprietà includeranno il nome del certificato.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-113">If the connection manager uses a client certificate, its properties include the certificate name.</span></span>  
  
-   <span data-ttu-id="1b0a4-114">Specificare il timeout per la connessione al server e le dimensioni del blocco per la scrittura dei dati.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-114">Provide a time-out for connecting to the server and a chunk size for writing data.</span></span>  
  
-   <span data-ttu-id="1b0a4-115">Utilizzo di un server proxy.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-115">Use a proxy server.</span></span> <span data-ttu-id="1b0a4-116">È inoltre possibile configurare il server proxy in modo da utilizzare credenziali e da ignorare il server proxy e utilizzare indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-116">The proxy server can also be configured to use credentials and to bypass the proxy server and use local addresses instead.</span></span>  
  
## <a name="configuration-of-the-http-connection-manager"></a><span data-ttu-id="1b0a4-117">Configurazione della gestione connessione HTTP</span><span class="sxs-lookup"><span data-stu-id="1b0a4-117">Configuration of the HTTP Connection Manager</span></span>  
 <span data-ttu-id="1b0a4-118">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-118">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="1b0a4-119">Per ulteriori informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b0a4-119">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="1b0a4-120">Editor gestione connessione HTTP &#40;pagina Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1b0a4-120">HTTP Connection Manager Editor &#40;Server Page&#41;</span></span>](../http-connection-manager-editor-server-page.md)  
  
-   [<span data-ttu-id="1b0a4-121">Editor gestione connessione HTTP &#40;pagina Proxy&#41;</span><span class="sxs-lookup"><span data-stu-id="1b0a4-121">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../http-connection-manager-editor-proxy-page.md)  
  
 <span data-ttu-id="1b0a4-122">Per informazioni sulla configurazione di una gestione connessione a livello di codice, vedere <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span><span class="sxs-lookup"><span data-stu-id="1b0a4-122">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0a4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b0a4-123">See Also</span></span>  
 <span data-ttu-id="1b0a4-124">[Attività servizio Web](../control-flow/web-service-task.md) </span><span class="sxs-lookup"><span data-stu-id="1b0a4-124">[Web Service Task](../control-flow/web-service-task.md) </span></span>  
 [<span data-ttu-id="1b0a4-125">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1b0a4-125">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
