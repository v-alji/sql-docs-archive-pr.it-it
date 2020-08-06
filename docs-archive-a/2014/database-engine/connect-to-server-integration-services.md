---
title: Connetti al server (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.dtsserver.f1
ms.assetid: 5be897bd-f36c-4c6a-a91a-13d0d016f8b6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8821018c45fdd77c4b3b896afc47b8f5b425af88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724143"
---
# <a name="connect-to-server-integration-services"></a><span data-ttu-id="72678-102">Connetti al server (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="72678-102">Connect to Server (Integration Services)</span></span>
  <span data-ttu-id="72678-103">Usare questa finestra di dialogo per visualizzare o specificare le opzioni per la connessione a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72678-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="72678-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="72678-104">Options</span></span>  
 <span data-ttu-id="72678-105">**Tipo di server**</span><span class="sxs-lookup"><span data-stu-id="72678-105">**Server type**</span></span>  
 <span data-ttu-id="72678-106">Per la registrazione di un server da Esplora oggetti, selezionare il tipo di server a cui connettersi, ovvero [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services.</span><span class="sxs-lookup"><span data-stu-id="72678-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="72678-107">Nelle altre parti della finestra di dialogo vengono visualizzate solo le opzioni applicabili al tipo di server selezionato.</span><span class="sxs-lookup"><span data-stu-id="72678-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="72678-108">Durante la registrazione di un server da Server registrati, la casella Tipo server è di sola lettura e corrisponde al tipo di server visualizzato nel componente Server registrati.</span><span class="sxs-lookup"><span data-stu-id="72678-108">When registering a server from Registered Servers, the Server type box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="72678-109">Per registrare un tipo diverso di server, selezionare [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services o Integration Services nella barra degli strumenti Server registrati prima di avviare la registrazione di un nuovo server.</span><span class="sxs-lookup"><span data-stu-id="72678-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="72678-110">**Nome server**</span><span class="sxs-lookup"><span data-stu-id="72678-110">**Server name**</span></span>  
 <span data-ttu-id="72678-111">Consente di selezionare il server a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72678-111">Select the server to connect to.</span></span> <span data-ttu-id="72678-112">Per impostazione predefinita verrà visualizzata l'ultima istanza del server a cui è stata effettuata la connessione.</span><span class="sxs-lookup"><span data-stu-id="72678-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72678-113">Non usare *\<servername>* \\ *\<instancename>* , perché non [!INCLUDE[ssIS](../includes/ssis-md.md)] supporta più istanze in un computer.</span><span class="sxs-lookup"><span data-stu-id="72678-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="72678-114">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="72678-114">**Authentication**</span></span>  
 <span data-ttu-id="72678-115">Solo l'autenticazione di [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows è disponibile per [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72678-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="72678-116">Tale modalità consente di connettersi tramite un account utente di Windows.</span><span class="sxs-lookup"><span data-stu-id="72678-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="72678-117">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="72678-117">**User name**</span></span>  
 <span data-ttu-id="72678-118">Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72678-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="72678-119">**Password**</span><span class="sxs-lookup"><span data-stu-id="72678-119">**Password**</span></span>  
 <span data-ttu-id="72678-120">Questa opzione non è disponibile in quanto per [!INCLUDE[ssIS](../includes/ssis-md.md)]è possibile utilizzare solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72678-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="72678-121">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="72678-121">**Connect**</span></span>  
 <span data-ttu-id="72678-122">Fare clic su questo pulsante per connettersi al server selezionato.</span><span class="sxs-lookup"><span data-stu-id="72678-122">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="72678-123">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="72678-123">**Options**</span></span>  
 <span data-ttu-id="72678-124">Fare clic su questo pulsante per visualizzare ulteriori opzioni per la connessione al server, come le opzioni per la registrazione di un server e la memorizzazione della password.</span><span class="sxs-lookup"><span data-stu-id="72678-124">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
