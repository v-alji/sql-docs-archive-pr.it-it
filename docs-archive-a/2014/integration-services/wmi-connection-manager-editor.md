---
title: Editor gestione connessione WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmiconnection.f1
helpviewer_keywords:
- WMI Connection Manager Editor
ms.assetid: 0ef2c913-0779-4a07-989e-3361cd83170b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e85cdd2157c8ebe4cb9e6b53f8c3b47ff102a7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636764"
---
# <a name="wmi-connection-manager-editor"></a><span data-ttu-id="63998-102">Editor gestione connessione WMI</span><span class="sxs-lookup"><span data-stu-id="63998-102">WMI Connection Manager Editor</span></span>
  <span data-ttu-id="63998-103">Usare la finestra di dialogo **Editor gestione connessioni WMI** per specificare una connessione del servizio Strumentazione gestione Windows (WMI) a un server.</span><span class="sxs-lookup"><span data-stu-id="63998-103">Use the **WMI Connection Manager** dialog box to specify a Microsoft Windows Management Instrumentation (WMI) connection to a server.</span></span>  
  
 <span data-ttu-id="63998-104">Per ulteriori informazioni sulla gestione connessioni WMI, vedere [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="63998-104">To learn more about the WMI connection manager, see [WMI Connection Manager](connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="63998-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="63998-105">Options</span></span>  
 <span data-ttu-id="63998-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="63998-106">**Name**</span></span>  
 <span data-ttu-id="63998-107">Consente di specificare un nome univoco per la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="63998-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="63998-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="63998-108">**Description**</span></span>  
 <span data-ttu-id="63998-109">Consente di aggiungere una descrizione per la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="63998-109">Describe the connection manager.</span></span> <span data-ttu-id="63998-110">È consigliabile includere nella descrizione informazioni sugli scopi della gestione connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="63998-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="63998-111">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="63998-111">**Server name**</span></span>  
 <span data-ttu-id="63998-112">Consente di specificare il nome del server al quale si desidera connettersi tramite WMI.</span><span class="sxs-lookup"><span data-stu-id="63998-112">Provide the name of the server to which you want to make the WMI connection.</span></span>  
  
 <span data-ttu-id="63998-113">**Spazio dei nomi**</span><span class="sxs-lookup"><span data-stu-id="63998-113">**Namespace**</span></span>  
 <span data-ttu-id="63998-114">Consente di specificare lo spazio dei nomi WMI.</span><span class="sxs-lookup"><span data-stu-id="63998-114">Specify the WMI namespace.</span></span>  
  
 <span data-ttu-id="63998-115">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="63998-115">**Use Windows authentication**</span></span>  
 <span data-ttu-id="63998-116">Selezionare questa opzione per utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="63998-116">Select to use Windows Authentication.</span></span> <span data-ttu-id="63998-117">Se si utilizza l'autenticazione di Windows non è necessario specificare un nome utente o una password per la connessione.</span><span class="sxs-lookup"><span data-stu-id="63998-117">If you use Windows Authentication, you do not need to provide a user name or password for the connection.</span></span>  
  
 <span data-ttu-id="63998-118">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="63998-118">**User name**</span></span>  
 <span data-ttu-id="63998-119">Se non si utilizza l'autenticazione di Windows è necessario specificare un nome utente per la connessione.</span><span class="sxs-lookup"><span data-stu-id="63998-119">If you do not use Windows Authentication, you must provide a user name for the connection.</span></span>  
  
 <span data-ttu-id="63998-120">**Password**</span><span class="sxs-lookup"><span data-stu-id="63998-120">**Password**</span></span>  
 <span data-ttu-id="63998-121">Se non si utilizza l'autenticazione di Windows è necessario specificare una password per la connessione.</span><span class="sxs-lookup"><span data-stu-id="63998-121">If you do not use Windows Authentication, you must provide the password for the connection.</span></span>  
  
 <span data-ttu-id="63998-122">**Test**</span><span class="sxs-lookup"><span data-stu-id="63998-122">**Test**</span></span>  
 <span data-ttu-id="63998-123">Consente di verificare le impostazioni della gestione connessioni.</span><span class="sxs-lookup"><span data-stu-id="63998-123">Test the connection manager settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63998-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63998-124">See Also</span></span>  
 <span data-ttu-id="63998-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="63998-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="63998-126">[Concetti relativi al provider WMI per la gestione della configurazione](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="63998-126">[WMI Provider for Configuration Management Concepts](../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="63998-127">Concetti relativi al provider WMI per eventi del server</span><span class="sxs-lookup"><span data-stu-id="63998-127">WMI Provider for Server Events Concepts</span></span>](../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)  
  
  
