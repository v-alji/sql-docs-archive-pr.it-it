---
title: Connetti al server (pagina Nome account di accesso) - Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724139"
---
# <a name="connect-to-server-login-page-integration-services"></a><span data-ttu-id="287ae-102">Connetti al server (pagina Nome account di accesso) - Integration Services</span><span class="sxs-lookup"><span data-stu-id="287ae-102">Connect to Server (Login Page) Integration Services</span></span>
  <span data-ttu-id="287ae-103">Utilizzare questa scheda per visualizzare o specificare le opzioni seguenti per la connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="287ae-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="287ae-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="287ae-104">Options</span></span>  
 <span data-ttu-id="287ae-105">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="287ae-105">**Server type**</span></span>  
 <span data-ttu-id="287ae-106">Per la registrazione di un server da Esplora oggetti, selezionare il tipo di server a cui connettersi, ovvero [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services.</span><span class="sxs-lookup"><span data-stu-id="287ae-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="287ae-107">Nelle altre parti della finestra di dialogo vengono visualizzate solo le opzioni applicabili al tipo di server selezionato.</span><span class="sxs-lookup"><span data-stu-id="287ae-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="287ae-108">Durante la registrazione di un server da Server registrati, la casella **Tipo server** è di sola lettura e corrisponde al tipo di server visualizzato nel componente Server registrati.</span><span class="sxs-lookup"><span data-stu-id="287ae-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="287ae-109">Per registrare un tipo diverso di server, selezionare [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services nella barra degli strumenti Server registrati prima di avviare la registrazione di un nuovo server.</span><span class="sxs-lookup"><span data-stu-id="287ae-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="287ae-110">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="287ae-110">**Server name**</span></span>  
 <span data-ttu-id="287ae-111">Consente di selezionare il server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="287ae-111">Select the server to connect to.</span></span> <span data-ttu-id="287ae-112">Per impostazione predefinita verrà visualizzata l'ultima istanza del server a cui è stata effettuata la connessione.</span><span class="sxs-lookup"><span data-stu-id="287ae-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="287ae-113">Non usare *\<servername>* \\ *\<instancename>* , perché non [!INCLUDE[ssIS](../includes/ssis-md.md)] supporta più istanze in un computer.</span><span class="sxs-lookup"><span data-stu-id="287ae-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="287ae-114">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="287ae-114">**Authentication**</span></span>  
 <span data-ttu-id="287ae-115">Solo l'autenticazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows è disponibile per [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="287ae-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="287ae-116">Tale modalità consente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="287ae-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="287ae-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="287ae-117">**User name**</span></span>  
 <span data-ttu-id="287ae-118">Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="287ae-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="287ae-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="287ae-119">**Password**</span></span>  
 <span data-ttu-id="287ae-120">Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="287ae-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="287ae-121">**Memorizza password**</span><span class="sxs-lookup"><span data-stu-id="287ae-121">**Remember password**</span></span>  
 <span data-ttu-id="287ae-122">Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="287ae-122">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="287ae-123">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="287ae-123">**Connect**</span></span>  
 <span data-ttu-id="287ae-124">Consente di connettersi al server selezionato.</span><span class="sxs-lookup"><span data-stu-id="287ae-124">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="287ae-125">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="287ae-125">**Options**</span></span>  
 <span data-ttu-id="287ae-126">Fare clic su questo pulsante per modificare la finestra di dialogo e nascondere le opzioni aggiuntive per la connessione al server, ad esempio le opzioni per la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="287ae-126">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
