---
title: Gestione connessione SMTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], SMTP
- SMTP connection manager [Integration Services]
- connection managers [Integration Services], SMTP
ms.assetid: 3795d442-714b-4bbb-9acd-75bf277a468a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f3c090ab672790901baae01ae86f8d22e008b4ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724868"
---
# <a name="smtp-connection-manager"></a><span data-ttu-id="fa6db-102">Gestione connessione SMTP</span><span class="sxs-lookup"><span data-stu-id="fa6db-102">SMTP Connection Manager</span></span>
  <span data-ttu-id="fa6db-103">Una gestione connessione SMTP consente a un pacchetto di connettersi a un server SMTP (Simple Mail Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="fa6db-103">An SMTP connection manager enables a package to connect to a Simple Mail Transfer Protocol (SMTP) server.</span></span> <span data-ttu-id="fa6db-104">La gestione connessione SMTP viene usata dall'attività Invia messaggi inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fa6db-104">The Send Mail task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an SMTP connection manager.</span></span>  
  
 <span data-ttu-id="fa6db-105">Quando si utilizza Microsoft Exchange come server SMTP, potrebbe essere necessario configurare la gestione connessione SMTP per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fa6db-105">When using Microsoft Exchange as the SMTP server, you may need to configure the SMTP connection manager to use Windows Authentication.</span></span> <span data-ttu-id="fa6db-106">È possibile configurare i server Exchange in modo da non consentire connessioni SMTP non autenticate.</span><span class="sxs-lookup"><span data-stu-id="fa6db-106">Exchange servers may be configured to not allow unauthenticated SMTP connections.</span></span>  
  
## <a name="configuration-the-smtp-connection-manager"></a><span data-ttu-id="fa6db-107">Configurazione della gestione connessione SMTP</span><span class="sxs-lookup"><span data-stu-id="fa6db-107">Configuration the SMTP Connection Manager</span></span>  
 <span data-ttu-id="fa6db-108">Quando si aggiunge una gestione connessione SMTP a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione SMTP, imposta le proprietà della gestione connessione e quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="fa6db-108">When you add an SMTP connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an SMTP connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="fa6db-109">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `SMTP`.</span><span class="sxs-lookup"><span data-stu-id="fa6db-109">The `ConnectionManagerType` property of the connection manager is set to `SMTP`.</span></span>  
  
 <span data-ttu-id="fa6db-110">Per configurare la gestione connessione SMTP, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="fa6db-110">You can configure an SMTP connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="fa6db-111">Specificare una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="fa6db-111">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="fa6db-112">Specificare il nome di un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="fa6db-112">Specify the name of an SMTP server.</span></span>  
  
-   <span data-ttu-id="fa6db-113">Specificare il metodo di autenticazione da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="fa6db-113">Specify the authentication method to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="fa6db-114">La gestione connessione SMTP supporta solo l'autenticazione anonima e l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="fa6db-114">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="fa6db-115">Non supporta l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="fa6db-115">It does not support basic authentication.</span></span>  
  
-   <span data-ttu-id="fa6db-116">Specificare se crittografare la comunicazione mediante SSL (Secure Sockets Layer) quando si inviano messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fa6db-116">Specify whether to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
 <span data-ttu-id="fa6db-117">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fa6db-117">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="fa6db-118">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione SMTP](../smtp-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="fa6db-118">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [SMTP Connection Manager Editor](../smtp-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="fa6db-119">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="fa6db-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
